---
apdl: "SABS"
method: sabs
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.sabs
generated: 2026-08-22
tags: [mapdl-command]
---

# SABS

PyMAPDL: `mapdl.sabs(key='', **kwargs)`

Specifies absolute values for element table operations.

## Parameters

**key**

Absolute value key:

- `0` - Use algebraic values in operations.
- `1` - Use absolute values in operations.

## Notes

Causes absolute values to be used in the [[sadd|SADD]], [[smult|SMULT]], [[smax|SMAX]], [[smin|SMIN]], and [[ssum|SSUM]] operations.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SABS.html
