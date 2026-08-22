# Solver lifecycle cells: design record

Claude drafted record of the 2026-08-22 evening discussion that produced notebook cells 1 to 5 in ` run_double_wall.ipynb`. Parked for the step 3 revisit in the planner. John's own note is `Ansys\Starter notes\3 - Solver at start.md`, which still carries the four route version and needs his rewrite.

## Decisions, in the order they were made

- Server and client are separate things and the notebook shows it: one cell starts a server (`launch_mapdl_process`, no client), one attaches a client (`Mapdl(ip, port)`), one terminates. The combined `launch_mapdl` is not used.
- The start cell looks before launching (port check), so it is safe to rerun. This is the lock file fix: a live server holds `file.lock` open, Windows refuses to delete it, `override=True` cannot clear a live lock.
- No magic numbers: `launcher.LOCALHOST`, `launcher.MAPDL_DEFAULT_PORT`. No hand written defaults: `nproc=2` was PyMAPDL's default echoed by hand and was dropped.
- Launch arguments, each a decision: `run_location` (repo scratch, else a random temp dir), `port` (the contract every client reads), `override=True` (clears a stale lock after a crash), `mapdl_output` (console log to a file so the undrained pipe can never block the server).
- One always run cell for imports and names, including the viewer setup since the trame env var must precede the pyvista import. Import style `import ansys.mapdl.core.launcher as launcher`.
- Termination is polite: a throwaway client sends EXIT. `close_all_local_instances` and `pymapdl stop` end in `proc.kill()`, no licence release. `exit()` on a client that did not launch the server is ignored unless `force=True`.
- Expensive sweeps must be reopenable: `SAVE,RUN,db` before EXIT, and db with rst in one folder per run, `scratch\runs\<RUN>\`, via `/CWD` plus `/FILNAME,RUN,1`. Not sorted by type: a results file is only readable against its mesh. A named folder in a chosen place is a real gain over the Workbench `_files\dp0\SYS\MECH\` burial.
- RUN name chosen once per sitting in cell 1.
- Flows: normal sitting 1, 2, 4. Clean rebuild 3, 2, 4. Kernel restart 1, 4. Back into an old sweep 1, 2, 4, 5.

## Verified by test (port 50060, scratchpad folder, never the live 50052)

- `launch_mapdl_process` on Windows returns before the port is bound (it waits for the .err file). A rerun within seconds saw nothing listening and collided on the lock. Cell 2 now polls the port for up to 60 s after launching.
- `get_process_at_port` reports the rank that holds the port, not the PID the launcher returns.
- Rerun guard holds (0.1 s, no second launch). Attach at Begin level and in PREP7. Save lands in the run folder. EXIT clears `file.lock`. Fresh launch, RESUME restores mesh and components. Repeat termination overwrites cleanly. Termination with nothing listening is a no-op.
- `/FILNAME` is Begin level only and a survivor left in PREP7 makes it raise `MapdlInvalidRoutineError`. Cell 4 issues `finish()` first.
- The server writes `jobname.db` into its cwd on EXIT by itself, independent of PyMAPDL. The explicit SAVE is the deliberate full copy; the EXIT rewrite lands on the same name a moment later.
- `file.lock` stays in the scratch root for the server's whole life, untouched by `/CWD` and `/FILNAME`.
- Per rank files appear as `RUN0.*` and `RUN1.*` in the run folder (two ranks, the default nproc).

## Opus review, disposition

Taken: `/FILNAME` at PREP7, batch mode SAVE keeps no backup (cell 3 renames the old db to .dbb first), undrained pipes (`mapdl_output`), SCRATCH anchored on the repo root by walking to `.git`, dead `if RUN`, `proc.cwd()` dropped from the print (misleading after `/CWD`, can raise), a printed note when `RUN.rst` already exists.

Declined: lock cleanup path finding (test shows the lock gone after EXIT), TIME_WAIT guard on the port check, asserting ip and port against HOST and PORT (the port wait already proves a holder), selection scoped counts in the glance line.

Parked for the viewer note: setting `pyvista.global_theme.trame.jupyter_extension_enabled = False` and `server_proxy_enabled = False` after import reproduces native mode independent of import order, per the reviewer's reading of pyvista's theme code. Unverified here.

## Open items for the revisit

- Note 3 rewrite in John's words. Its route C (`Mapdl(ip, port).exit()` as the polite kill) is wrong as written: without `force=True` that exit is ignored.
- The TL sweep cell and `tl_sweep.run` know nothing about RUN: results land as `RUN.rst` through `/FILNAME`, but the `.npz` and `.png` names in `LLM\` are still fixed. Decide whether they take the run name.
- Whether `double_wall.py`'s `mapdl.clear()` leaves `/CWD` and the jobname alone (expected yes, not tested).
- The `pymapdl list -l` command as a terminal side status check, no kernel involved.
