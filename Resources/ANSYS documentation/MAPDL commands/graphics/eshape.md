---
apdl: "/ESHAPE"
method: eshape
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.eshape
generated: 2026-08-22
tags: [mapdl-command]
---

# /ESHAPE

PyMAPDL: `mapdl.eshape(scale='', key='', **kwargs)`

Displays elements with shapes determined from the real constants, section definition, or other inputs.

**Command default:**

Use simple display of line and area elements ( `SCALE` = 0).

## Parameters

**scale**

Scaling factor:

- `0` - Use simple display of line and area elements. This value is the default.
- `1` - Use real constants, section definition, or other information to form a solid shape display of the applicable elements.
- `FAC` - Multiply certain real constants, such as thickness, by `FAC` (where `FAC` \> 0.01) and use them to form a solid shape display of elements.

**key**

Current shell thickness key:

- `0` - Use current thickness in the displaced solid shape display of shell elements (valid for `SHELL181`, `SHELL208`, `SHELL209`, and `SHELL281` ). This value is the default.
- `1` - Use initial thickness in the displaced solid shape display of shell elements.

## Notes

The **/ESHAPE** command allows beams, shells, current sources, and certain special-purpose elements or elements with special options to be displayed as solids with the shape determined from the real constants, section types, or other information. Elements are displayed via the [[eplot|EPLOT]] command. No checks for valid or complete input are made for the display.

Following are details about using this command with various element types:

- `COMBIN14`, `COMBIN39`, and `MASS21` are displayed with a graphics icon, with the offset determined by the real constants and KEYOPT settings.
- `BEAM188`, `BEAM189`, `PIPE288`, `PIPE289` and `ELBOW290` are displayed as solids with the shape determined via the section-definition commands ( [[sectype|SECTYPE]] and [[secdata|SECDATA]] ). The arbitrary section option ( `Subtype` = ASEC) has no definite shape and appears as a thin rectangle to indicate the orientation; the thin side represents the beam Y axis and the thick (longer) side represents the Z axis. The length of thick side is determined by `TKz`. If `TKz` = 0, the area is used to determine the length of thick side. The thin side is scaled by the fraction of the thick side, regardless of `TKy`. If the offsets are defined via `CGy` / `CGz` ( [[secdata|SECDATA]] or [[secoffset|SECOFFSET]],USER, `OFFSETY`, `OFFSETZ` ), they are applied to the plot without scaling. The elements are displayed with internal lines representing the cross- section mesh.
- Reduced-integration and lower-order shells ( `SHELL181` and `SHELL208` with KEYOPT(3)=0) are displayed with uniform thickness, evaluated at the centroid, to reflect the element behavior.
- `SOLID272` and `SOLID273` are displayed as solids with the shape determined via the section- definition commands ( [[sectype|SECTYPE]] and [[secdata|SECDATA]] ). The 2D master plane is revolved around the prescribed axis of symmetry.
- `PLANE182`, `PLANE183`, `PLANE222`, and `PLANE223` with KEYOPT(3) = 6 are displayed as 3D solids with the shape determined by nodal locations and displacements at the nodes.
- Contour plots are available for these elements in postprocessing for PowerGraphics only ( [[graphics|/GRAPHICS]],POWER). To view 3D deformed shapes for the elements, issue [[outres|OUTRES]],MISC or [[outres|OUTRES]],ALL for static or transient analyses. To view 3D mode shapes for a modal or eigenvalue buckling analysis, expand the modes with element results calculation ON ( `Elcalc` = YES for [[mxpand|MXPAND]] ).
- `SOURC36`, `CIRCU124`, and `TRANS126` elements always plot using **/ESHAPE** when PowerGraphics is activated ( [[graphics|/GRAPHICS]],POWER).

In most cases, **/ESHAPE** renders a thickness representation of your shell, plane and layered elements more readily in PowerGraphics ( [[graphics|/GRAPHICS]],POWER). This type of representation employs PowerGraphics to generate the enhanced representation, and will often provide no enhancement in Full Graphics ( [[graphics|/GRAPHICS]],FULL). This is especially true for POST1 results displays, where **/ESHAPE** is not supported for most element types with FULL graphics.

When PowerGraphics is active, **/ESHAPE** may degrade the image if adjacent elements have overlapping material, such as shell elements which are not co-planar. Additionally, if adjacent elements have different thicknesses, the polygons depicting the connectivity between the "thicker" and "thinner" elements along the shared element edges may not always be displayed.

For POST1 results displays (such as [[plnsol|PLNSOL]] ), the following limitations apply:

- If you issue [[rsys|RSYS]],SOLU before reviewing results for beam or pipe elements, contour plots for displacement (for example, [[plnsol|PLNSOL]],U,X and [[pldisp|PLDISP]] ) do not appear in the solution coordinate system when **/ESHAPE** is active. Instead, the contours appear in the global Cartesian coordinate system.
- When shell elements are not co-planar, the resulting [[plnsol|PLNSOL]] display with **/ESHAPE** will actually be a [[plesol|PLESOL]] display as the non-coincident pseudo-nodes are not averaged. Additionally, **/ESHAPE** should not be used with coincident elements because the plot may incorrectly average the displacements of the coincident elements.
- When nodes are initially coincident and PowerGraphics is active, duplicate polygons are eliminated to conserve display time and disk space. The command may degrade the image if initially coincident nodes have different displacements. The tolerance for determining coincidence is 1E-9 times the model's bounding box diagonal.
- If you want to view solution results ( [[plnsol|PLNSOL]], etc.) on layered elements (such as `SHELL181`, `SOLSH190`, `SOLID185` Layered Solid, `SOLID186` Layered Solid, `SHELL208`, `SHELL209`, `SHELL281`, and `ELBOW290` ), set KEYOPT(8) = 1 for the layer elements so that the data for all layers is stored in the results file.
- You can plot the through-thickness temperatures of elements `SHELL131` and `SHELL132` regardless of the thermal DOFs in use by issuing the [[plnsol|PLNSOL]],TEMP command (with PowerGraphics and **/ESHAPE** active).
- The **/ESHAPE**,1 and **/ESHAPE**, `FAC` commands are incompatible with the [[cycexpand|/CYCEXPAND]] command used in cyclic symmetry analyses.
- The **/ESHAPE**,1 command does not support velocity and acceleration results for elements `PLANE182`, `PLANE183`, `PLANE222`, or `PLANE223` with KEYOPT(3) = 6.
- For coupled-field elements `PLANE222` and `PLANE223` with KEYOPT(3) = 6, the **/ESHAPE** command can be used to visualize structural results. Non-structural results visualization is limited to gradient and flux displays supported with PowerGraphics.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESHAPE.html
