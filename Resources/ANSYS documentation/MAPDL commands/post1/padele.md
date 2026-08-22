---
apdl: "PADELE"
method: padele
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.padele
generated: 2026-08-22
tags: [mapdl-command]
---

# PADELE

PyMAPDL: `mapdl.padele(delopt='', **kwargs)`

Deletes a defined path.

**Command default:**

Deletes the currently active path.

## Parameters

**delopt**

Path delete option (one of the following):

- `ALL` - Delete all defined paths.
- `NAME` - Delete a specific path from the list of path definitions. (Substitute the actual path name for NAME.)

## Notes

Paths are identified by individual path names. To review the current list of path names, issue the command [[path|PATH]],STATUS.

This command is valid in the general postprocessor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PADELE.html
