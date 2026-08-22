---
apdl: "EMORE"
method: emore
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.emore
generated: 2026-08-22
tags: [mapdl-command]
---

# EMORE

PyMAPDL: `mapdl.emore(q='', r='', s='', t='', u='', v='', w='', x='', **kwargs)`

Adds more nodes to the just-defined element.

## Parameters

**q**, **r**, **s**, **t**, **u**, **v**, **w**, **x**: Numbers of nodes typically assigned to ninth (node `Q` ) through sixteenth (node `X` ) nodal positions, if any. If `Q` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

## Notes

Repeat **EMORE** command for up to 4 additional nodes (20 maximum). Nodes are added after the last nonzero node of the element. Node numbers defined with this command may be zeroes.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EMORE.html
