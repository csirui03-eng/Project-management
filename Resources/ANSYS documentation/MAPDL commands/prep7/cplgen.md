---
apdl: "CPLGEN"
method: cplgen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.coupled_dof.CoupledDof.cplgen
generated: 2026-08-22
tags: [mapdl-command]
---

# CPLGEN

PyMAPDL: `mapdl.cplgen(nsetf='', lab1='', lab2='', lab3='', lab4='', lab5='', **kwargs)`

Generates sets of coupled nodes from an existing set.

## Parameters

**nsetf**: Generate sets from existing set `NSETF`.

**lab1**, **lab2**, **lab3**, **lab4**, **lab5**: Generate sets with these labels (see [[cp|CP]] command for valid labels). Sets are numbered as the highest existing set number + 1.

## Notes

Generates additional sets of coupled nodes (with different labels) from an existing set ( [[cp|CP]], [[cpngen|CPNGEN]] ). The same node numbers are included in the generated sets. If all labels of nodes are to be coupled and the nodes are coincident, the [[nummrg|NUMMRG]] command should be used to automatically redefine the node number (for efficiency).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CPLGEN.html
