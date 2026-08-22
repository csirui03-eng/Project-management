# Solver at start

Written 2026-08-22, after a night of lock file collisions. The single point of failure was one assumption: that restarting the kernel restarts the solver. It does not. The solver is a separate OS process. The kernel holds only a phone line to it, and a kernel restart hangs up the phone without telling the other end anything.

## The facts underneath

- `launch_mapdl` spawns MAPDL as an independent process (two ANSYS.exe ranks with `nproc=2`, distributed run, jobnames file0 and file1). It outlives kernel restarts, crashes, and closed tabs.
- While alive it holds `file.lock` in its run location open. Windows refuses to delete an open file, so a second launch into the same folder dies with "unable to remove lock file". That is the guard working, not breaking.
- We pin `run_location` to the repo scratch folder so files stay findable and out of both repos. The docs default is a fresh random temp dir per launch, which is why the guides never show this collision: default users cannot have it, they just accumulate invisible orphans in temp instead.
- `cleanup_on_exit=True` closes the solver only on a polite kernel exit. Force restarts and crashes skip it.
- The docs treat "connect to an already running session" as a first class route, equal to launching. Attaching is not a hack.

## Status check before anything

First cell of the notebook: look before touching. Reports whether a solver is listening, whether the lock is held, and what model it carries. Then choose a route.

```python
# --- solver status: run first, then pick a start route ---------------------
import socket
from pathlib import Path

SCRATCH = Path.cwd().parent / "scratch"
s = socket.socket(); s.settimeout(0.5)
alive = s.connect_ex(("127.0.0.1", 50052)) == 0
s.close()
print("port 50052 :", "solver listening" if alive else "nothing listening")
print("file.lock  :", "present" if (SCRATCH / "file.lock").exists() else "absent")
if alive:
    from ansys.mapdl.core import Mapdl
    probe = Mapdl(ip="127.0.0.1", port=50052)
    print("model held :", len(probe.geometry.anum), "areas,", len(probe.geometry.lnum), "lines")
    del probe
```

## The four start routes

**A. Fresh start, nothing running.** Status says nothing listening. Plain launch.

```python
mapdl = launch_mapdl(run_location=str(SCRATCH), nproc=2, override=True, cleanup_on_exit=True)
```

**B. Attach to the survivor.** Status says solver listening and the model held is the one you want. Instant, no rebuild, the warm state is a feature.

```python
mapdl = Mapdl(ip="127.0.0.1", port=50052)
```

**C. Close the survivor, then launch clean.** Status says solver listening but you want a known clean slate. Attach and exit is the polite kill: the solver releases its license and lock on the way out.

```python
try:
    Mapdl(ip="127.0.0.1", port=50052).exit()
    import time; time.sleep(2)
except Exception:
    pass
mapdl = launch_mapdl(run_location=str(SCRATCH), nproc=2, override=True, cleanup_on_exit=True)
```

**D. Broom the machine, then launch.** Several instances suspected, or state unknown. The official one liner from the launcher module.

```python
from ansys.mapdl.core.launcher import close_all_local_instances
close_all_local_instances()
mapdl = launch_mapdl(run_location=str(SCRATCH), nproc=2, override=True, cleanup_on_exit=True)
```

## Which one when

- Sitting down to continue: status, then B. The model is already built and the attach costs nothing.
- After editing element types or anything where inherited state could lie: C. The rebuild is one `%run` cell, cheap insurance.
- Lock error or confusion about what is running: D, then A.
- Never: killing ANSYS.exe from Task Manager while a session might be live. One of those processes is the worker rank of the session you are using.

Related: [[1 Environment set up|Environment set up]] for the env and kernel model, [[4 Interactive viewer|Interactive viewer]] for the plotting stack.
