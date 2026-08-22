---
apdl: "PAGET"
method: paget
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.paget
generated: 2026-08-22
tags: [mapdl-command]
---

# PAGET

PyMAPDL: `mapdl.paget(parray='', popt='', **kwargs)`

Writes current path information into an array variable.

## Parameters

**parray**: The name of the array parameter that Mechanical APDL creates to store the path information. If the array parameter already exists, it will be replaced with the current path information.

**popt**

Determines how data will be stored in the parameter specified with `PARRAY` :

- `POINTS` - Store the path points, the nodes (if any), and coordinate system. (For information on defining paths and path points, see the descriptions of the [[path|PATH]] and [[ppath|PPATH]] commands.)
- `TABLE` - Store the path data items. (See the [[pdef|PDEF]] command description for path data items.)
- `LABEL` - Stores path data labels.

## Notes

Use the **PAGET** command with the [[paput|PAPUT]] command to store and retrieve path data in array variables for archiving purposes.

When retrieving path information, restore the path points (POINTS option) first, then the path data (TABLE option), and then the path labels (LABEL option).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PAGET.html
