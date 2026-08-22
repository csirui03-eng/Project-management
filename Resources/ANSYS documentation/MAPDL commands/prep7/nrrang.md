---
apdl: "NRRANG"
method: nrrang
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.nrrang
generated: 2026-08-22
tags: [mapdl-command]
---

# NRRANG

PyMAPDL: `mapdl.nrrang(nmin='', nmax='', ninc='', **kwargs)`

Specifies the range of nodes to be read from the node file.

## Parameters

**nmin**, **nmax**, **ninc**: Node range is defined from `NMIN` (defaults to 1) to `NMAX` (defaults to 999999999) in steps of `NINC` (defaults to 1).

## Notes

Defines the range of nodes to be read ( [[nread|NREAD]] ) from the node file. Also implies an element range since only elements fully attached to these nodes will be read from the element file.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NRRANG.html
