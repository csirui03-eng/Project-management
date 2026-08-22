---
apdl: "PSPRNG"
method: psprng
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.piping.Piping.psprng
generated: 2026-08-22
tags: [mapdl-command]
---

# PSPRNG

PyMAPDL: `mapdl.psprng(nloc='', type_='', k='', dx='', dy='', dz='', elem='', **kwargs)`

Defines a spring constraint in a piping run.

## Parameters

**nloc**: Node where spring is to be placed. Defaults to current run starting point.

**type_**

Type of spring:

- `TRAN` - Translational (default).
- `ROT` - Rotational.

**k**: Spring constant value (must be positive).

**dx**, **dy**, **dz**: Increment (in terms of the active coordinate system components) to determine spring ground point. Spring length must not be zero. Constraints are automatically generated at the ground point.

**elem**: Element number to be assigned to spring (defaults to the previous maximum element number (MAXEL + 1)).

## Notes

Defines a spring constraint (spring element `COMBIN14` ) at a given location in a piping run. (See the RUN command description in [Archived Commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/Hlp_C_VALVE.html).)

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSPRNG.html
