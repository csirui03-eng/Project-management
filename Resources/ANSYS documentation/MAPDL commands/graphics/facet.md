---
apdl: "/FACET"
method: facet
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.facet
generated: 2026-08-22
tags: [mapdl-command]
---

# /FACET

PyMAPDL: `mapdl.facet(lab='', **kwargs)`

Specifies the facet representation used to form solid model displays.

## Parameters

**lab**

Valid labels:

- `FINE` - Use finer tessellation to increase the number of facets for the display. Provides the best representation (but decreases speed of operation).
- `NORML` - Use the basic number of facets for the display (default).
- `COAR` - Use a limited number of facets for the display. This option will increase the speed of the operations, but may produce poor representations for some imported models.
- `WIRE` - Display model with a wireframe representation (fast, but surfaces will not be shown).

## Notes

Specifies the facet (or polygon) representation used to form solid model displays. Used only with the [[aplot|APLOT]], [[asum|ASUM]], [[vplot|VPLOT]], and [[vsum|VSUM]] commands.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FACET.html
