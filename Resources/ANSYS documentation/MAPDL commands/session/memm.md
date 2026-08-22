---
apdl: "MEMM"
method: memm
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.memm
generated: 2026-08-22
tags: [mapdl-command]
---

# MEMM

PyMAPDL: `mapdl.memm(lab='', kywrd='', **kwargs)`

Allows the current session to keep allocated memory

## Parameters

**lab**: When `Lab` = KEEP, the memory manager's ability to acquire and keep memory is controlled by `Kywrd`

**kywrd**

Turns the memory "keep" mode on or off

- `ON` - Keep any memory allocated during the analysis.
- `OFF` - Use memory dynamically and free it up to other users after use (default).

## Notes

You can use the **MEMM** command to ensure that memory intensive operations will always have the same memory available when the operations occur intermittently. Normally, if a large amount of memory is allocated for a specific operation, it will be returned to the system once the operation is finished. This option always maintains the highest level used during the analysis until the analysis is finished.

The **MEMM** command does not affect the value you specify with the -m switch. When you allocate memory with the -m switch, that amount will always be available. However, if dynamic memory allocation in excess of the -m value occurs, you can use the **MEMM** command to ensure that amount is retained until the end of your analysis.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MEMM.html
