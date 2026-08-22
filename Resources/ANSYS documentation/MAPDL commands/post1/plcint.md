---
apdl: "PLCINT"
method: plcint
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.plcint
generated: 2026-08-22
tags: [mapdl-command]
---

# PLCINT

PyMAPDL: `mapdl.plcint(action='', id_='', node='', cont='', dtype='', **kwargs)`

Plots the fracture parameter ( [[cint|CINT]] ) result data.

## Parameters

**action**

- `PATH` - Plots [[cint|CINT]] quantities according to path number (default).
- `FRONT` - Plots [[cint|CINT]] quantities distribution along the crack front.

**id_**: Crack ID number.

**node**

Crack tip node number (default = ALL).

Use only for `ACTION` = PATH. Plots [[cint|CINT]] contour for an individual crack tip node.

**cont**

Contour number (Default = ALL).

Use only for `ACTION` = FRONT. Plots [[cint|CINT]] distribution along the crack for a given path.

**dtype**

Data type to output:

- `JINT` - J-integral (default)
- `IIN1` - Interaction integral 1
- `IIN2` - Interaction integral 2
- `IIN3` - Interaction integral 3
- `K1` - Mode 1 stress-intensity factor
- `K2` - Mode 2 stress-intensity factor
- `K3` - Mode 3 stress-intensity factor
- `G1` - Mode 1 energy release rate
- `G2` - Mode 2 energy release rate
- `G3` - Mode 3 energy release rate
- `GT` - Total energy release rate
- `MFTX` - Total material force X
- `MFTY` - Total material force Y
- `MFTZ` - Total material force Z
- `TSTRESS` - T-stress
- `CEXT` - Crack extension
- `CSTAR` - C2-integral

## Notes

The **PLCINT** command is not available for [XFEM-based crack-growth](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemreferences) analyses results processing.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLCINT.html
