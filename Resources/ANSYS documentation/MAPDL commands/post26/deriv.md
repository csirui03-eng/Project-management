---
apdl: "DERIV"
method: deriv
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.deriv
generated: 2026-08-22
tags: [mapdl-command]
---

# DERIV

PyMAPDL: `mapdl.deriv(ir='', iy='', ix='', name='', facta='', **kwargs)`

Differentiates a variable.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to NV ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result.

**iy**, **ix**: Reference numbers of variables to be operated on. `IY` is differentiated with respect to `IX`.

**name**: Thirty-two character name for identifying the variable on printouts and displays. Embedded blanks are compressed for output.

**facta**: Scaling factor (positive or negative) applied as shown below (defaults to 1.0).

## Notes

Differentiates variables according to the operation:

`IR` = `FACTA` x d( `IY` )/d( `IX` )

Variable `IX` must be in ascending order.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DERIV.html
