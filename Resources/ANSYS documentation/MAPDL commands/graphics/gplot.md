---
apdl: "GPLOT"
method: gplot
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.gplot
generated: 2026-08-22
tags: [mapdl-command]
---

# GPLOT

PyMAPDL: `mapdl.gplot(**kwargs)`

Controls general plotting.

## Notes

This command displays all entity types as specified via the [[gtype|/GTYPE]] command. Only selected entities ( [[nsel|NSEL]], [[esel|ESEL]], [[ksel|KSEL]], [[lsel|LSEL]], [[asel|ASEL]], [[vsel|VSEL]] ) will be displayed. See the descriptions of the [[gtype|/GTYPE]] and [[gcmd|/GCMD]] commands for methods of setting the entity types displayed.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GPLOT.html
