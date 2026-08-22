---
apdl: "FTSIZE"
method: ftsize
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1._fatigue.Fatigue.ftsize
generated: 2026-08-22
tags: [mapdl-command]
---

# FTSIZE

PyMAPDL: `mapdl.ftsize(mxloc='', mxev='', mxlod='', **kwargs)`

Defines the fatigue data storage array.

## Parameters

**mxloc**: Maximum number of fatigue locations (defaults to 5).

**mxev**: Maximum number of fatigue events (defaults to 10).

**mxlod**: Maximum number of loadings in each event (defaults to 3).

## Notes

Defines the size and erases the stress conditions for the fatigue data storage array. A stress condition is a loading (stresses) at a particular location (node) for a particular event. Size is defined in terms of the maximum number of locations, events, and loadings. The array size cannot be changed once data storage has begun (without erasing all previously stored data). If a size change is necessary, see the [[ftwrite|FTWRITE]] command.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FTSIZE.html
