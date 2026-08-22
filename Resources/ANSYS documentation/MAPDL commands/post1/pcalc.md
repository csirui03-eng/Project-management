---
apdl: "PCALC"
method: pcalc
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.pcalc
generated: 2026-08-22
tags: [mapdl-command]
---

# PCALC

PyMAPDL: `mapdl.pcalc(oper='', labr='', lab1='', lab2='', fact1='', fact2='', const='', **kwargs)`

Forms additional labeled path items by operating on existing path items.

## Parameters

**oper**

Type of operation to be performed. See [Notes](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_PCALC.html#eqb7ec3fe5-6192 - 4739-ab47-6047369573ed) below for specific descriptions of each operation:

- `ADD` - Adds two existing path items.
- `MULT` - Multiplies two existing path items.
- `DIV` - Divides two existing path items (a divide by zero results in a value of zero).
- `EXP` - Exponentiates and adds existing path items.
- `DERI` - Finds a derivative.
- `INTG` - Finds an integral.
- `SIN` - Sine.
- `COS` - Cosine.
- `ASIN` - Arcsine.
- `ACOS` - Arccosine.
- `LOG` - Natural log.

**labr**: Label assigned to the resulting path item.

**lab1**: First labeled path item in operation.

**lab2**: Second labeled path item in operation. `Lab2` must not be blank for the MULT, DIV, DERI, and INTG operations.

**fact1**: Factor applied to `Lab1`. A (blank) or '0' entry defaults to 1.0.

**fact2**: Factor applied to `Lab2`. A (blank) or '0' entry defaults to 1.0.

**const**: Constant value (defaults to 0.0).

## Notes

If `Oper` = ADD, the command format is:

**PCALC**,ADD, `LabR`, `Lab1`, `Lab2`, `FACT1`, `FACT2`, `CONST`

This operation adds two existing path items according to the operation:

`LabR` = ( `FACT1` x `Lab1` ) + ( `FACT2` x `Lab2` ) + `CONST`

It may be used to scale the results for a single path item.

If `Oper` = MULT, the command format is:

**PCALC**,MULT, `LabR`, `Lab1`, `Lab2`, `FACT1`

`Lab2` must not be blank. This operation multiplies two existing path items according to the operation:

`LabR` = `Lab1` x `Lab2` x `FACT1`

If `Oper` = DIV, the command format is:

**PCALC**,DIV, `LabR`, `Lab1`, `Lab2`, `FACT1`

`Lab2` must not be blank. This operation divides two existing path items according to the operation:

`LabR` = ( `Lab1` / `Lab2` ) x `FACT1`

If `Oper` = EXP, the command format is:

**PCALC**,EXP, `LabR`, `Lab1`, `Lab2`, `FACT1`, `FACT2`

This operation exponentiates and adds existing path items according to the operation:

`LabR` = (\| `Lab1` \| <sup>FACT1</sup> ) + (\| `Lab2` \| <sup>FACT2</sup> \|)

If `Oper` = DERI, the command format is:

**PCALC**,DERI, `LabR`, `Lab1`, `Lab2`, `FACT1`

`Lab2` must not be blank. This operation finds a derivative according to the operation:

`LabR` = `FACT1` x d( `Lab1` )/d( `Lab2` )

If `Oper` = INTG, the command format is:

**PCALC**,INTG, `LabR`, `Lab1`, `Lab2`, `FACT1`

`Lab2` must not be blank. This operation finds an integral according to the operation:

(equation not available in the PyMAPDL source, see the Ansys help page)

Use S for `Lab2` to integrate `Lab1` with respect to the path length. S, the distance along the path, is automatically calculated by the program when a path item is created with the [[pdef|PDEF]] command.

If `Oper` = SIN, COS, ASIN, ACOS, or LOG, the command format is:

**PCALC**,Oper, `LabR`, `Lab1`, `FACT1`, `CONST`

where the function (SIN, COS, ASIN, ACOS or LOG) is substituted for `Oper` and `Lab2` is blank.

The operation finds the resulting path item according to one of the following formulas:

`LabR` = FACT2 x `sin(FACT1 x Lab1) + CONST`

`LabR` = FACT2 x `cos(FACT1 x Lab1) + CONST`

`LabR` = FACT2 x `sin` -1(FACT1 x Lab1) + CONST

`LabR` = FACT2 x `cos` -1(FACT1 x Lab1) + CONST

`LabR` = FACT2 x `log(FACT1 x Lab1) + CONST`

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PCALC.html
