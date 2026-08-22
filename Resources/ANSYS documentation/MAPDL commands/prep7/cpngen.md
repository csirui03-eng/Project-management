---
apdl: "CPNGEN"
method: cpngen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.coupled_dof.CoupledDof.cpngen
generated: 2026-08-22
tags: [mapdl-command]
---

# CPNGEN

PyMAPDL: `mapdl.cpngen(nset='', lab='', node1='', node2='', ninc='', **kwargs)`

Defines, modifies, or adds to a set of coupled degrees of freedom.

## Parameters

**nset**: Set reference number ( [[cp|CP]] ).

**lab**: Degree of freedom label ( [[cp|CP]] ).

**node1**, **node2**, **ninc**: Include in coupled set nodes `NODE1` to `NODE2` in steps of `NINC` (defaults to 1). If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). If - `NODE1`, delete range of nodes from set instead of including. A component name may also be substituted for `NODE1` ( `NODE2` and `NINC` are ignored).

## Notes

Defines, modifies, or adds to a set of coupled degrees of freedom. May be used in combination with (or in place of) the [[cp|CP]] command. Repeat **CPNGEN** command for additional nodes.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CPNGEN.html
