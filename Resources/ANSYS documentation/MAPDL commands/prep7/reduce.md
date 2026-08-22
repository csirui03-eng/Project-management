---
apdl: "REDUCE"
method: reduce
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.piping.Piping.reduce
generated: 2026-08-22
tags: [mapdl-command]
---

# REDUCE

PyMAPDL: `mapdl.reduce(nloc='', leng='', elem='', **kwargs)`

Defines a reducer in a piping run.

## Parameters

**nloc**: Node where two straight pipes intersect at center of reducer. Defaults to previous run starting point.

**leng**: Length of reducer (defaults to average pipe OD).

**elem**: Element number to be assigned to reducer (defaults to MAXEL + 1).

## Notes

Defines a reducer (straight-pipe element PIPE16 with averaged specifications) in place of the intersection of two previously defined straight pipe elements in a piping run. (See the RUN command description in [Archived Commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/Hlp_C_VALVE.html).) Two new nodes are generated at the ends of the reducer. The two straight pipes are automatically "shortened" to meet the ends of the reducer. The reducer specifications and loadings are taken from the corresponding two straight pipes.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_REDUCE.html
