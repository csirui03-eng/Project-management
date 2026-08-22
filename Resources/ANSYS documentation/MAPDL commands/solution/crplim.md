---
apdl: "CRPLIM"
method: crplim
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution._nonlinear_options.NonlinearOptions.crplim
generated: 2026-08-22
tags: [mapdl-command]
---

# CRPLIM

PyMAPDL: `mapdl.crplim(crcr='', option='', **kwargs)`

Specifies the creep criterion for automatic time stepping.

## Parameters

**crcr**: Value of creep criteria for the creep limit ratio control.

**option**

Type of creep analysis for which the creep limit ratio is specified :

- `1 (or ON)` - Implicit creep analysis.
- `0 (or OFF)` - Explicit creep analysis.

## Notes

The [[cutcontrol|CUTCONTROL]] command can also be used to set the creep criterion and is preferred over this command for setting automatic time step controls.

The creep ratio control can be used at the same time for implicit creep and explicit creep analyses. For implicit creep ( `Option` = 1), the default value of `CRCR` is zero (that is, no creep limit control), and you can specify any value. For explicit creep ( `Option` = 0), the default value of `CRCR` is 0.1, and the maximum value allowed is 0.25.

This command is also valid in PREP7.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CRPLIM.html
