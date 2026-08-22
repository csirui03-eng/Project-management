---
apdl: "/PSF"
method: psf
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.psf
generated: 2026-08-22
tags: [mapdl-command]
---

# /PSF

PyMAPDL: `mapdl.psf(item='', comp='', key='', kshell='', color='', **kwargs)`

Shows surface load symbols on model displays.

**Command default:**

No surface load symbols are displayed.

## Parameters

**item**, **comp**: Labels identifying the surface load to be shown; see */PSF - Valid Item and Component Labels*.

**key**

Key to turn surface load symbols on or off:

- `0` - Off (default).
- `1` - On, shown as face outlines. Line surface loads ( [[sfl|SFL]] ) on solid model plots are shown as arrows.
- `2` - On, shown as arrows.
- `3` - On, shown as color filled surfaces. Line and area surface loads ( [[sfl|SFL]] and [[sfa|SFA]] ) on solid model plots are shown as arrows.

**kshell**

Visibility key for shell elements.

- `0` - Off (default), surface load symbols are displayed only on visible load faces.
- `1` - On, surface load symbols are displayed even if load face is not visible.

**color**

Visibility key for contour legend.

- `ON` - The symbols (arrows or face outlines) will show up in color with the legend showing the corresponding color labels (default).
- `OFF` - The contour legend will not be displayed. The symbols (arrows or face outlines) will show up in grey. The size of the arrows will be proportional to the applied load.

## Notes

**/PSF** determines whether and how to show surface loads on subsequent model displays.

If surface loads are applied to solid model entities, only solid model plots show the load symbols; node and element plots do not show them unless the loads are transferred ( [[sftran|SFTRAN]] or [[sbctran|SBCTRAN]] ). Similarly, solid model plots do not show the load symbols if surface loads are applied to nodes and elements. For node and element plots of shell element models, the surface load symbols are shown only if the load face is visible from the current viewing direction.

The effects of the **/PSF** command are not cumulative (that is, the command does not modify an existing setting from a previously issued **/PSF** command). Only the setting specified via the most recent **/PSF** command applies.

If you issue a [postprocessing (POST1)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_CH2_7.html#cmdpost1failure) plot command that produces result contours (such as [[plnsol|PLNSOL]] ), **/PSF** has no effect. This behavior prevents conflicting contours in the graphics window.

When using the radiosity method ( `Item` = RDSF and `Comp` = ENCL) with `Key` = 2, the radiation arrows point outward from any element face.

**/PSF**,STAT displays current **/PSF** settings, and **/PSF**,DEFA resets them back to default.

Other useful commands are [[pnum|/PNUM]],SVAL,1 to show the values of the surface loads, [[vscale|/VSCALE]] to change arrow lengths, and [[pbc|/PBC]] and [[pbf|/PBF]] to activate other load symbols.

For beam elements, only the colors representing shear (GREEN) and normal (RED) pressures are displayed for the arrows. The color of these arrows does not correspond to the magnitudes in the contour legend. The length of these arrows does, however, correlate to the relative magnitude of the pressures.

For elements `SURF159`, `SOLID272`, `SOLID273`, `PIPE288` and `PIPE289`, **/PSF** is not available when displaying elements with shapes determined from the real constants or section definition ( [[eshape|/ESHAPE]] ). For `PIPE288` and `PIPE289`, only external loads applied via [[sfbeam|SFBEAM]] are displayed.

This command is valid in any processor.

### /PSF - Valid Item and Component Labels

| Item | Comp | Description | Comments |
|----|----|----|----|
| PRES | NORM (or blank) | Applied pressure normal to the face (real component only). | For element types other than `SURF153`, `SURF154` and `SURF156`. |
|  | NORM | Applied pressure normal to the face (real component). | For element types `SURF153`, `SURF154` and `SURF156` with KEYOPT(2) = 0. For [supported structural elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SFCONTROL.html#) with `KCSYS` = 0. |
|  | TANX | Applied pressure in the element tangential x direction (real component). |  |
|  | TANY | Applied pressure in the element tangential- y direction (real component). |  |
|  | INRM | Applied pressure normal to the face (imaginary component). |  |
|  | ITNX | Applied pressure in the element tangential x direction (imaginary component). |  |
|  | ITNY | Applied pressure in the element tangential y direction (imaginary component). |  |
|  | LOCX | Applied pressure in the local x direction (real component). | For element types `SURF153`, `SURF154` and `SURF156` with KEYOPT(2) = 1. For [supported structural elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SFCONTROL.html#) with `KCSYS` = 1. |
|  | LOCY | Applied pressure in the local y direction (real component). |  |
|  | LOCZ | Applied pressure in the local z direction (real component). |  |
|  | ILCX | Applied pressure in the local x direction (imaginary component). |  |
|  | ILCY | Applied pressure in the local y direction (imaginary component). |  |
|  | ILCZ | Applied pressure in the local z direction (imaginary component). |  |
|  | RVEC | Applied pressure in the user-defined direction (real component). | For [supported structural elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SFCONTROL.html#) with `KCSYS` = 2. |
|  | IVEC | Applied pressure in the user-defined direction (imaginary component). |  |
| CONV | HCOEF | Applied convection (film coefficient). |  |
|  | TBULK | Applied convection (bulk temperature). |  |
| RAD | EMIS | Applied radiation (emissivity). |  |
|  | TAMB | Applied radiation (ambient temperature). |  |
| RDSF | EMSS | Radiation emissivity. |  |
|  | ENCL | Enclosure number. |  |
| FSIN |  | Fluid-solid interface number. |  |
| HFLUX |  | Applied heat flux. |  |
| FSI |  | Acoustic fluid-structure interface flag. |  |
| IMPD |  | Applied acoustic impedance. |  |
| SHLD | COND | Applied conductivity. |  |
|  | MUR | Applied relative permeability. |  |
| MXWF |  | Maxwell force flag. |  |
| INF |  | Exterior surface flag. |  |
| CHRGS |  | Applied electric surface charge density. |  |
| BLI |  | Boundary layer impedance flag. |  |

Pressure loads apply to the element coordinate system (KEYOPT(2) = 0). Adjust appropriately for a local coordinate system (KEYOPT(2) = 1). See, and in the Element Reference.

`KCSYS` is specified when issuing [[sfcontrol|SFCONTROL]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSF.html
