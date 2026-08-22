---
apdl: "SUCALC"
method: sucalc
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.surface_operations.SurfaceOperations.sucalc
generated: 2026-08-22
tags: [mapdl-command]
---

# SUCALC

PyMAPDL: `mapdl.sucalc(rsetname='', lab1='', oper='', lab2='', fact1='', fact2='', const='', **kwargs)`

Create new result data by operating on two existing result data sets on a given surface.

## Parameters

**rsetname**: Eight character name for new result data.

**lab1**: First result data upon which to operate.

**oper**

Mathematical operation to perform.

- `ADD` - ( `lab1` + `lab2` + `const` )
- `SUB` - ( `lab1` - `lab2` + `const` )
- `MULT` - ( `lab1` \* `lab2` + `const` )
- `DIV` - ( `lab1` / `lab2` + `const` )
- `EXP` - ( `lab1` ^ `fact1` + `lab2` ^ `fact2` + `const` )
- `COS` - (cos ( `lab1` ) + `const` )
- `SIN` - (sin ( `lab1` ) + `const` )
- `ACOS` - (acos ( `lab1` ) + `const` )
- `ASIN` - (asin ( `lab1` ) + `const` )
- `ATAN` - (atan ( `lab1` ) + `const` )
- `ATA2` - (atan2 ( `lab1` / `lab2` ) + `const` )
- `LOG` - (log ( `lab1` ) + `const` )
- `ABS` - (abs ( `lab1` ) + `const` )
- `ZERO` - (0 + `const` )

**lab2**: Second result data upon which to operate.

**fact1**: First scaling factor (for EXP option only).

**fact2**: Second scaling factor (for EXP option only).

**const**: Constant added to the values in the resulting data.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SUCALC.html
