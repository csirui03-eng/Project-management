# Servers

Started 2026-08-22. Concept note beside the numbered steps, feeds [[3 - Solver at start|Solver at start]].

## What a server is

A server is a process that on start claims an address and does no work until a request arrives at that address from a client. Answering a request does not terminate the process. Of course, being a process, when it is started it lives in memory, and between requests it sits there parked, zero CPU, until the OS hands it the next message.

## Server and client in MAPDL terms

## IP, port, PID

## Servers on this machine

| Server | Protocol | Where it listens | What it serves |
|---|---|---|---|
| MAPDL | gRPC | 127.0.0.1:50052 | the model and the solver |
| JupyterLab | HTTP and WebSocket | 127.0.0.1:8888 | the notebook UI to the browser |
| Jupyter kernel | ZMQ | five local ports, hidden | code execution for the Lab server |
| trame | WebSocket | inside the kernel, a port per viewer | the 3D viewer to the notebook |
| Ansys license manager | FlexLM | a port on the license host | permission to run |

Reference if wanted: [[2026-08-22 Servers, LLM draft]].
