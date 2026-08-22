---
apdl: "EPLOT"
method: eplot
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.eplot
generated: 2026-08-22
tags: [mapdl-command]
---

# EPLOT

PyMAPDL: `mapdl.eplot(**kwargs)`

PyMAPDL overrides `mapdl.eplot` with its own wrapper, so the signature above is not what `mapdl.eplot` runs. Reach the APDL command as text: `mapdl.run("EPLOT,...")`.

Produces an element display.

## Notes

Produces an element display of the selected elements. In full graphics, only those elements faces with all of their corresponding nodes selected are plotted. In PowerGraphics, all element faces of the selected element set are plotted irrespective of the nodes selected. However, for both full graphics and PowerGraphics, adjacent or otherwise duplicated faces of 3D solid elements will not be displayed in an attempt to eliminate plotting of interior facets. See the [[dsys|DSYS]] command for display coordinate system issues.

This command will display curvature in midside node elements when PowerGraphics is activated ( [[graphics|/GRAPHICS]] ,POWER) and [[efacet|/EFACET]],2 or [[efacet|/EFACET]],4 are enabled. (To display curvature, two facets per edge is recommended ( [[efacet|/EFACET]],2)). When you specify [[efacet|/EFACET]],1, PowerGraphics does not display midside nodes. [[efacet|/EFACET]] has no effect on **EPLOT** for non- midside node elements.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EPLOT.html
