---
apdl: "DELETE"
method: delete
group: aux3
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux3.results_files.ResultsFiles.delete
generated: 2026-08-22
tags: [mapdl-command]
---

# DELETE

PyMAPDL: `mapdl.delete(set_='', nstart='', nend='', **kwargs)`

Specifies sets in the results file to be deleted before postprocessing.

## Parameters

**set_**: Specifies that sets in the results file are to be deleted.

**nstart**: The first set in a results file to be deleted.

**nend**: The final set in a results file to be deleted. This field is used only if deleting more than one sequential sets.

## Notes

**DELETE** is a specification command that flags sets in the results file for deletion. It should be followed by a [[compress|COMPRESS]] command, the corresponding action command that deletes the specified sets.

The **DELETE** command is valid only in the results file editing processor (auxiliary processor AUX3).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DELETE.html
