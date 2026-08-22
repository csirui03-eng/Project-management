---
apdl: "NUMVAR"
method: numvar
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.numvar
generated: 2026-08-22
tags: [mapdl-command]
---

# NUMVAR

PyMAPDL: `mapdl.numvar(nv='', **kwargs)`

Specifies the number of variables allowed in POST26.

## Parameters

**nv**: Allow storage for `NV` variables. 200 maximum are allowed. Defaults to 10. TIME (variable 1) should also be included in this number.

## Notes

Specifies the number of variables allowed for data read from the results file and for data resulting from an operation (if any). For efficiency, `NV` should not be larger than necessary. `NV` cannot be changed after data storage begins.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NUMVAR.html
