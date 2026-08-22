---
apdl: "/AUX3"
method: aux3
group: aux3
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux3.results_files.ResultsFiles.aux3
generated: 2026-08-22
tags: [mapdl-command]
---

# /AUX3

PyMAPDL: `mapdl.aux3(**kwargs)`

Enters the results file editing processor.

## Notes

Enters the results-file editing processor (auxiliary processor AUX3), used for editing Mechanical APDL results files.

A pending [[delete|DELETE]] is processed when [[finish|FINISH]] or `/EOF` is issued. To cancel a pending [[delete|DELETE]], issue [[undelete|UNDELETE]].

This command is valid only at the Begin Level.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AUX3_sl.html
