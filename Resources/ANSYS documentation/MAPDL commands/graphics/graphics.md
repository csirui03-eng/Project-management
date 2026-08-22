---
apdl: "/GRAPHICS"
method: graphics
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.graphics
generated: 2026-08-22
tags: [mapdl-command]
---

# /GRAPHICS

PyMAPDL: `mapdl.graphics(key='', **kwargs)`

Defines the type of graphics display.

## Parameters

**key**

Graphics key:

- `FULL` - Display all model geometry and results.
- `POWER` - Activate PowerGraphics (default when GUI is on).

## Notes

The **/GRAPHICS** command specifies the type of graphics display. `Key` = POWER activates the PowerGraphics capability. PowerGraphics offers faster plotting than the `Key` = FULL option, and speeds up element, results, area, line, and volume displays.

The default PowerGraphics mode is enabled automatically when accessing the GUI. This action supersedes all prior macros or start-up routines ( `start.ans`, `config.ans`, etc.). Full graphics mode is accessed only by issuing **/GRAPHICS**,FULL after the GUI is active.

Results values (both printed and plotted) may differ between the `Key` = FULL  
and `Key` = POWER options because each option specifies a different set of data for

averaging and display. For `Key` = FULL, all element and results values (interior and surface) are included. For `Key` = POWER, only element and results values along the model exterior surface are processed.

When `Key` = FULL, it is possible to deselect an individual node, select all elements (including the element that contains that node), and then perform postprocessing calculations on those elements and have that unselected node not be considered in those calculations. If PowerGraphics is active, however, postprocessing always displays based on selected elements.

If you have specified one facet per element edge for PowerGraphics displays (via the [[efacet|/EFACET]] command or options from the General Postproc or Utility menu), PowerGraphics does not plot midside nodes. ( [[efacet|/EFACET]] applies to element type displays only.)

Maximum values shown in plots can differ from printed maximum values. This is due to different averaging schemes used for plotted and printed maximum values.

When using solution coordinate systems for results output ( [[rsys|RSYS]],SOLU) with PowerGraphics, the deformed or displaced shape in a POST1 contour display can be unexpected (although the contours are displayed in the expected colors). The program does not rotate displacement values (Ux,Uy,Uz) to global; instead, the displacements (stored locally) are added directly to the global coordinates (X,Y,Z). For example, if in PREP7 the nodes are rotated 90 degrees about the z axis and the global Uy displacements are relatively large, the Ux values will be large, causing the model to display a large deformation in the global X direction.

PowerGraphics displays do not average at geometric discontinuities. The printouts in PowerGraphics will, however, provide averaging information at geometric discontinuities if the models do not contain shell elements. Carefully inspect the data you obtain at geometric discontinuities.

PowerGraphics does not support the following diffusion analysis results: CONC, CG, DF, EPDI.

`Key` = FULL is not available for [XFEM-based crack-growth analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_frac/Hlp_G_FRACXFEM.html#fracxfemreferences).

Excepting a few options, PowerGraphics supports these commands:

(table not available in the PyMAPDL source, see the Ansys help page)

The following commands are executed via the `Key` = FULL option, regardless of whether PowerGraphics is activated:

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GRAPHICS.html
