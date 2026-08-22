# Servers

LLM draft from the 2026-08-22 solver discussion, parked here as reference material. John's own note is [[X - Servers]] in Starter notes.

## What a server is

A server is a process that starts, claims an address, and then waits. It does nothing on its own. It answers requests that arrive at that address, from other processes called clients, and keeps running after each answer so the next request finds it still there. The client sends a message, the server does the work and replies, the client may then go away. The server stays.

That is the whole idea. Everything else is detail about what address, what message format, and what work.

Three consequences follow from it, and all three bit us with MAPDL:

- A server has its own lifetime. It is not part of any client. Closing the client (restarting the kernel) hangs up the phone and the server never notices.
- A server can hold state between requests. MAPDL holds the whole model. That is why attaching to a survivor costs nothing and why inherited state can lie after a rebuild.
- Several clients can talk to one server. Our notebook and Claude's audit scripts are two clients on one solver, and selections made by one are seen by the other.

## The three identifiers

- PID belongs to the operating system. Every running process has one, server or not. It is how a process is found and killed (`taskkill /PID`).
- IP says which machine. 127.0.0.1 is this one.
- Port says which program on that machine. A number 0 to 65535 that a server claims when it starts. Two servers cannot hold the same port on one IP, which is why a second MAPDL goes to 50053.

PID is "which process". IP plus port is "where to phone it". Some servers listen on a file path instead of a port (named pipes on Windows, Unix sockets on Linux).

## Server and client, in MAPDL terms

The server is the solver: `ANSYS.exe -grpc` listening on a port, holding the model, doing the meshing and solving, owning file.lock. The client is the Python `Mapdl` object in the kernel, a phone line and nothing more. Each `mapdl.et(...)` call is one gRPC message down that line.

| Function | Starts the server | Creates a client |
|---|---|---|
| `launch_mapdl_process()` | yes | no, returns ip, port, PID |
| `Mapdl(ip, port)` | no | yes, attaches to whatever is listening |
| `launch_mapdl()` | yes | yes, both in one call |

`pymapdl start` on the command line wraps the first. It lets the solver be started once, from a terminal, before Jupyter is open, with clients coming and going afterwards.

## The servers already running on this machine

| Server | Protocol | Where it listens | What it serves |
|---|---|---|---|
| MAPDL | gRPC | 127.0.0.1:50052 | the model and the solver |
| JupyterLab | HTTP and WebSocket | 127.0.0.1:8888 | the notebook UI to the browser |
| Jupyter kernel | ZMQ | five local ports, hidden | code execution for the Lab server |
| trame | WebSocket | inside the kernel, a port per viewer | the 3D viewer to the notebook |
| Ansys license manager | FlexLM | a port on the license host | permission to run |

MAPDL and JupyterLab are separate servers with separate PIDs. Restarting one never touches the other. Beyond the machine, the shape repeats: GitHub (HTTPS and SSH) for the repos, a database server for queries, a file server for shares, a DNS server turning names into IPs. The protocol differs, the shape does not: a process with a PID, listening at an address, answering clients.

## Open questions

- What the gRPC message for one MAPDL command looks like on the wire, and whether that matters for anything we do.
- Whether the trame port per viewer is why stale viewers pile up after many plots.
