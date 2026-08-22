---
apdl: "INT1"
method: int1
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.int1
generated: 2026-08-22
tags: [mapdl-command]
---

# INT1

PyMAPDL: `mapdl.int1(ir='', iy='', ix='', name='', facta='', factb='', const='', **kwargs)`

Integrates a variable.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to `NV` ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result. Table values represent integrated sum of `IY` to current table position of `IX`.

**iy**, **ix**: Integrate variable `IY` with respect to `IX`.

**name**: Thirty-two character name for identifying the variable on the printout and displays. Embedded blanks are compressed upon output.

**facta**, **factb**: Scaling factors (positive or negative) applied to the corresponding variables (default to 1.0).

**const**: Initial value.

## Notes

Integrates variables according to the operation:

`IR` = ∫ ( `FACTA` x `IY` ) d( `FACTB` x `IX` ) + `CONST`

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_INT1.html
