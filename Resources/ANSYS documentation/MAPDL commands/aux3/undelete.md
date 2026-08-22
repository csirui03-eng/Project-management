---
apdl: "UNDELETE"
method: undelete
group: aux3
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux3.results_files.ResultsFiles.undelete
generated: 2026-08-22
tags: [mapdl-command]
---

# UNDELETE

PyMAPDL: `mapdl.undelete(option='', nstart='', nend='', **kwargs)`

Removes results sets from the group of sets selected for editing.

## Parameters

**option**

Specifies which sets are to be removed from the selected sets.

- `SET` - Specifies one or more particular sets in the results file that are to be removed from the group of sets selected for deletion.
- `ALL` - Removes all selected sets that are currently selected for deletion.

**nstart**: The first set to be removed from the set selected for deletion.

**nend**: The final set to be removed from the set selected for deletion. This field is used only if operating on more than one sequential set.

## Notes

Use this command if you have previously marked a set for deletion (with the [[delete|DELETE]] command) and now wish to keep that set instead of deleting it.

The **UNDELETE** command is valid only in the results file editing processor (auxiliary processor AUX3), and, like the other AUX3 commands, it only affects the data steps index (DSI), time (TIM), loadstep, substep and cumulative step iteration (LSP) records in the results file.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_UNDELETE.html
