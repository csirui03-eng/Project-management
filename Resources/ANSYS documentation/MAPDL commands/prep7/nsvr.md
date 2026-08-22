---
apdl: "NSVR"
method: nsvr
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.element_type.ElementType.nsvr
generated: 2026-08-22
tags: [mapdl-command]
---

# NSVR

PyMAPDL: `mapdl.nsvr(itype='', nstv='', **kwargs)`

Defines the number of variables for user-programmable element options.

## Parameters

**itype**: Element type number as defined on the [[et|ET]] command.

**nstv**: Number of extra state variables to save (must be no more than 840).

## Notes

Defines the number of extra variables that need to be saved for user-programmable (system-dependent) element options, for example, material laws through user subroutine USERPL. `ITYPE` must first be defined with the [[et|ET]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NSVR.html
