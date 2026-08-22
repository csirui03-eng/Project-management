---
apdl: "*TOPER"
method: toper
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.toper
generated: 2026-08-22
tags: [mapdl-command]
---

# *TOPER

PyMAPDL: `mapdl.toper(parr='', par1='', oper='', par2='', fact1='', fact2='', con1='', **kwargs)`

Operates on table parameters.

## Parameters

**parr**: Name of the resulting table parameter. The command will create a table array parameter with this name. Any existing parameter with this name will be overwritten.

**par1**: Name of the first table parameter.

**oper**: The operation to be performed: ADD. The operation is: ParR(i,j,k) = FACT12Par1(i,j,k) + FACT2 \*Par2(i,j,k) +CON1

**par2**: Name of the second table parameter.

**fact1**: The first table parameter multiplying constant. Defaults to 1.

**fact2**: The second table parameter multiplying constant. Defaults to 1.

**con1**: The constant increment for offset. Defaults to 0.

## Notes

### Argument descriptions

- `parr : str` - Name of the resulting table parameter. The command will create a table array parameter with this name. Any existing parameter with this name will be overwritten.
- `par1 : str` - Name of the first table parameter.
- `oper : str` - The operation to be performed: ADD. The operation is: ParR(i,j,k) = FACT12Par1(i,j,k) + FACT2 \*Par2(i,j,k) +CON1
- `par2 : str` - Name of the second table parameter.
- `fact1 : str` - The first table parameter multiplying constant. Defaults to 1.
- `fact2 : str` - The second table parameter multiplying constant. Defaults to 1.
- `con1 : str` - The constant increment for offset. Defaults to 0.

**\*TOPER** operates on table parameters according to: ParR(i,j,k) = FACT12Par1(i,j,k) + FACT2 \*Par2(i,j,k) +CON1

Par1 and Par2 must have the same dimensions and the same variable names corresponding to those dimensions. Par1 and Par2 must also have identical index values for rows, columns, etc.

If you want a local coordinate system for the resulting array, you must dimension it as such using the [[dim|*DIM]] command before issuing **\*TOPER**.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TOPER_st.html
