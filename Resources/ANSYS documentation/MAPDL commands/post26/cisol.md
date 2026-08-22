---
apdl: "CISOL"
method: cisol
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.cisol
generated: 2026-08-22
tags: [mapdl-command]
---

# CISOL

PyMAPDL: `mapdl.cisol(n='', id_='', node='', cont='', dtype='', **kwargs)`

Stores fracture parameter information in a variable.

## Parameters

**n**: Arbitrary reference number or name assigned to this variable. Number must be \>1 but \</= NUMVAR.

**id_**: Crack ID number.

**node**: Crack tip node number.

**cont**: Contour number.

**dtype**

Data type to output:

- `JINT` - J-integral
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
- `CEXT` - Crack extension

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CISOL.html
