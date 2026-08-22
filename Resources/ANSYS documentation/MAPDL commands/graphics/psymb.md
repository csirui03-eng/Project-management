---
apdl: "/PSYMB"
method: psymb
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.psymb
generated: 2026-08-22
tags: [mapdl-command]
---

# /PSYMB

PyMAPDL: `mapdl.psymb(label='', key='', **kwargs)`

Shows various symbols on displays.

## Parameters

**label**

Show symbols as selected from the following labels:

- `CS` - Local coordinate systems.
- `NDIR` - Nodal coordinate systems (on rotated nodes only).
- `ESYS` - Element coordinate systems (element displays only).
- `LDIR` - Line directions (line displays only).
- `LDIV` - Controls the display of element divisions on lines.
- `ADIR` - Area direction symbol (for keypoint, line, area and volume plots).
- `LAYR` - Layer orientations (relative to the projected element x-axis) or fiber orientations in smeared reinforcing elements. Used only within an element display. Use `KEY` to specify the layer number.
- `ECON` - Element mesh symbols on keypoints and lines.
- `DOT` - Larger symbols displayed for node and keypoint locations. When `Label` = DOT, `KEY` = 1 by default.
- `XNOD` - Extra node of surface or circuit elements.
- `FBCS` - Force boundary condition scaling. Subsequent `KEY` value determines whether or not to scale the applied and derived forces/moments to the same maximum value.
- `DEFA` - Resets the symbol keys so that Mechanical APDL displays none of the symbols controlled by the **/PSYMB** command. The value of the `KEY` field is ignored.
- `STAT` - Prints the status of the settings of the symbol keys controlled by the **/PSYMB** command. The `KEY` field is ignored.
- `MARK` - Controls the marker size ( [[gmarker|/GMARKER]] ). When `Label` = MARK, `KEY` = 10 by default.

**key**

Symbol key:

- `-1` - Effective only if `Label` = LAYR and solid shape element display ( [[eshape|/ESHAPE]] ) is active. Orientation of all layers appears with the solid shape element display.
- `0` - No symbol (default). If `Label` = LDIV, then `KEY` = 0 indicates that the displayed element divisions will correspond to the existing mesh (the word MESHED or EXISTING can also be substituted). Also, for `Label` = LDIV, if you execute any meshing command (such as [[amesh|AMESH]] or [[vmesh|VMESH]] ), `KEY` is set to 0 (MESHED) automatically. If `Label` = FBCS, then `KEY` = 0 indicates that boundary condition scaling will not be common. The applied and derived forces/moments will be scaled to their respective maximum values.
- `1` - Include symbol. If `Label` = LDIV, then `KEY` = 1 indicates that the displayed line divisions will correspond to the value assigned by [[lesize|LESIZE]] (the word LESIZE can also be substituted). Also, for `Label` = LDIV, if you execute the [[lesize|LESIZE]] command, `KEY` is set to 1 (LESIZE) automatically. If `Label` = FBCS, then `KEY` = 1 indicates that boundary condition scaling will be common. The applied and derived forces/moments will be scaled to the same maximum value.
- `N` - If `Label` = LAYR, then `N` is equal to the layer number. If `Label` = DOT, then `N` can be equal to 0,1,.....15, indicating the dot size. If `Label` = MARK, then `N` can be equal to 1,.....10, indicating the marker size. If `Label` = LDIV, then `KEY` = -1, indicates that no element divisions will be displayed (the word OFF can also be substituted).

## Notes

Includes various symbols on the display. Triads are right-handed with x displayed as the longest leg. Where color is displayed, x is white, y is green, and z is blue. For beams, x is always along the length of the element. For lines, an arrow represents the direction of a line, from the beginning keypoint to the end keypoint. See [[plopts|/PLOPTS]] command for additional display options. Use [[pstatus|/PSTATUS]] or **/PSYMB**,STAT to display settings. Use **/PSYMB**,DEFA to reset all specifications back to their defaults. The command **/PSYMB**,ECON,1 causes the symbol "M" to be displayed on keypoints and lines associated with meshed entities. When you issue the command **/PSYMB**,DOT,1, a larger symbol is displayed for each node and keypoint location. Using **/PSYMB**,MARK,1, a smaller marker size can be displayed.

PowerGraphics ( [[graphics|/GRAPHICS]],POWER) does not support **/PSYMB**,ESYS and **/PSYMB**,LAYR.

If `KEY` = `N` and PowerGraphics is off, the centroid of the surface elements is connected to the extra node using a gray line. However, if PowerGraphics is on, the color of the line connecting the centroid to the extra node is the same as that for the elements themselves (as determined by [[pnum|/PNUM]] ).

When `Label` = LAYR, the layer systems can be visualized with all current-technology layered elements and the smeared reinforcing element `REINF265`. To use **/PSYMB**,LAYR with `REINF265`, first set the vector-mode graphics option ( [[device|/DEVICE]],VECTOR,1).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSYMB.html
