---
apdl: "NPLOT"
method: nplot
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.nplot
generated: 2026-08-22
tags: [mapdl-command]
---

# NPLOT

PyMAPDL: `mapdl.nplot(knum='', **kwargs)`

Displays nodes.

## Parameters

**knum**

Node number key:

- `0` - No node numbers on display.
- `1` - Include node numbers on display. See also [[pnum|/PNUM]] command.

## Notes

Produces a node display. Only selected nodes ( [[nsel|NSEL]] ) are displayed. Elements need not be defined. See the [[dsys|DSYS]] command for display coordinate system.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NPLOT.html
