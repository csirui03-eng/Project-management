---
apdl: "/MAP"
method: slashmap
group: map
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.map.pressure_mapping.PressureMapping.slashmap
generated: 2026-08-22
tags: [mapdl-command]
---

# /MAP

PyMAPDL: `mapdl.slashmap(**kwargs)`

Enters the mapping processor.

## Notes

Enters the mapping processor. This processor is used to read in source data from an external file and map it to the existing geometry.

The current database is saved (to `BeforeMapping.DB` ) upon entering the processor, and it is resumed upon exiting ( [[finish|FINISH]] command). Any nodes or elements not on the target surface are deleted for easier viewing of the mapping quantities. A database of this mapping geometry ( `Mapping.DB` ) is also saved at the [[finish|FINISH]] command.

This command is valid only at the Begin Level.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MAP_s.html
