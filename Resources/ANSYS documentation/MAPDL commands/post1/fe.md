---
apdl: "FE"
method: fe
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1._fatigue.Fatigue.fe
generated: 2026-08-22
tags: [mapdl-command]
---

# FE

PyMAPDL: `mapdl.fe(nev='', cycle='', fact='', title='', **kwargs)`

Defines a set of fatigue event parameters.

## Parameters

**nev**: Reference number for this event (within `MXEV` ).

**cycle**: Number of required cycles (defaults to 1). If -1, erase all parameters and fatigue stresses for this event.

**fact**: Scale factor to be applied to all loadings in this event (defaults to 1.0).

**title**: User defined identification title for this event (up to 20 characters).

## Notes

Repeat FE command to define additional sets of event parameters ( `MXEV` limit), to redefine event parameters, or to delete event stress conditions.

The set of fatigue event parameters is associated with all loadings and all locations. See the FTSIZE command for the maximum set of events ( `MXEV` ) allowed.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FE.html
