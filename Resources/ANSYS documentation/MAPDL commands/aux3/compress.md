---
apdl: "COMPRESS"
method: compress
group: aux3
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux3.results_files.ResultsFiles.compress
generated: 2026-08-22
tags: [mapdl-command]
---

# COMPRESS

PyMAPDL: `mapdl.compress(**kwargs)`

Deletes all specified sets.

## Notes

Issue this command to delete all sets specified with the [[delete|DELETE]] command.

The **COMPRESS** command is valid only in the results file editing processor (auxiliary processor AUX3), and, like the other AUX3 commands, it only affects the data steps index (DSI), time (TIM), loadstep, substep and cumulative step iteration (LSP) records in the results file.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_COMPRESS.html
