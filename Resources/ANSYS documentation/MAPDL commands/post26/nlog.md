---
apdl: "NLOG"
method: nlog
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.nlog
generated: 2026-08-22
tags: [mapdl-command]
---

# NLOG

PyMAPDL: `mapdl.nlog(ir='', ia='', name='', facta='', factb='', **kwargs)`

Forms the natural log of a variable.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to NV ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result.

**ia**: Reference number of the variable to be operated on.

**name**: Thirty-two character name identifying the variable on printouts and displays. Embedded blanks are compressed for output.

**facta**: Scaling factor applied to variable `IA` (defaults to 1.0).

**factb**: Scaling factor (positive or negative) applied to the operation (defaults to 1.0).

## Notes

Forms the natural log of a variable according to the operation:

`IR` = `FACTB` \*LN( `FACTA` x `IA` )

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NLOG.html
