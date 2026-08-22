---
apdl: "ATAN"
method: atan
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.atan
generated: 2026-08-22
tags: [mapdl-command]
---

# ATAN

PyMAPDL: `mapdl.atan(ir='', ia='', name='', facta='', **kwargs)`

Forms the arctangent of a complex variable.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to `NV` ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result.

**ia**: Reference number of the complex variable to be operated on.

**name**: Thirty-two character name for identifying the variable on the printout and displays. Embedded blanks are compressed upon output.

**facta**: Scaling factor (positive or negative) applied to variable `IA` (defaults to 1.0). Usually `FACTA` should be set to 1. `FACTA` may affect the position of the angle by a multiple of π, resulting in a quadrant change.

## Notes

Forms the arctangent of a complex variable according to the operation:

`IR` = ATAN( `FACTA` X b / a )

where a and b are the real and imaginary parts, respectively, of the complex variable `IA` (which is of the form a + i b ). The arctangent represents the phase angle (in radians), and is valid only for a harmonic analysis ( [[antype|ANTYPE]],HARMIC).

Since the scaling factor is applied uniformly to b / a, applying any positive or negative scaling factor will not affect the size of the phase angle, with the exception that a negative scaling factor will change the results quadrant by π. The magnitude of a complex number is still obtained through the [[abs|ABS]] command. See [POST26 - Data Operations](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_post10.html#eqbe42048a-448b-4de9-91a9-1c8007937622) in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html) for details.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ATAN.html
