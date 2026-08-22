---
apdl: "PAPUT"
method: paput
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.paput
generated: 2026-08-22
tags: [mapdl-command]
---

# PAPUT

PyMAPDL: `mapdl.paput(parray='', popt='', **kwargs)`

Retrieves path information from an array variable.

## Parameters

**parray**: Name of the array variable containing the path information.

**popt**

Specifies which path data to retrieve:

- `POINTS` - Retrieve path point information (specified with the [[ppath|PPATH]] command and stored with the [[paget|PAGET]],POINTS command). The path data name will be assigned to the path points.
- `TABLE` - Retrieve path data items (defined via the [[pdef|PDEF]] command and stored with the [[paget|PAGET]],,TABLE command).
- `LABEL` - Retrieve path labels stored with the [[paget|PAGET]],,LABEL command.

## Notes

When retrieving path information, restore path points (POINTS option) first, then the path data (TABLE option), and then the path labels (LABEL option).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PAPUT.html
