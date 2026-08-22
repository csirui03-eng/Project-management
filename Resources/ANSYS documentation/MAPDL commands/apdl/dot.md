---
apdl: "*DOT"
method: dot
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.dot
generated: 2026-08-22
tags: [mapdl-command]
---

# *DOT

PyMAPDL: `mapdl.dot(vector1='', vector2='', par_real='', par_imag='', conj='', **kwargs)`

Computes the dot (or inner) product of two vectors.

## Parameters

**vector1**: Name of first vector; must have been previously specified by a [[vec|*VEC]] command.

**vector2**: Name of second vector; must have been previously specified by a [[vec|*VEC]] command.

**par_real**: Parameter name that contains the result.

**par_imag**: Parameter name that contains the imaginary part of the result (used only for complex vectors).

**conj**

Key to specify use of the conjugate of `Vector1` when the vectors are complex:

- `TRUE` - Use the conjugate of `Vector1` (default).
- `FALSE` - Do not use the conjugate of `Vector1`.

## Notes

If `Vector1` and `Vector2` are complex, the complex conjugate of `Vector1` is used to compute the result ( `Par_Real`, `Par_Imag` ). Therefore, **\*DOT** applied to complex vectors performs the operation:

(equation not available in the PyMAPDL source, see the Ansys help page)

Set `Conj` = FALSE if you do not want to use the conjugate of `Vector1`. In this case, the operation is:

(equation not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DOT.html
