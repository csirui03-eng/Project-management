---
apdl: "PSPEC"
method: pspec
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.piping.Piping.pspec
generated: 2026-08-22
tags: [mapdl-command]
---

# PSPEC

PyMAPDL: `mapdl.pspec(mat='', dnom='', sched='', od='', tk='', **kwargs)`

Defines pipe material and dimensions.

## Parameters

**mat**: Material number referring to a material property \[ [[mp|MP]] \]. Material number must be between 1 and 40.

**dnom**, **sched**

Nominal diameter of pipe and schedule rating. Only valid ratings accepted. If these are specified, the `OD` and `TK` values are found from an internal table.

Valid values for `DNOM` are: 1, 1.5, 2, 2.5, 3, 3.5, 4, 5, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, and 36.

Valid ratings for `SCHED` are: 5, 5S, 10, 10S, 20, 30, 40, 40S, 60, 80 80S, 100, 120, 140, 160, XS, XXS, and STD.

**od**: Outer diameter of pipe (if `DNOM` not specified). If both `DNOM` and `OD` are not specified, `OD` and `TK` retain their previous values.

**tk**: Wall thickness of pipe (if `OD` specified).

## Notes

Defines pipe material and dimensions. (See the RUN command description in [Archived Commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/Hlp_C_VALVE.html).)

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSPEC.html
