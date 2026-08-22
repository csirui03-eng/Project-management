---
apdl: "LESIZE"
method: lesize
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.lesize
generated: 2026-08-22
tags: [mapdl-command]
---

# LESIZE

PyMAPDL: `mapdl.lesize(nl1='', size='', angsiz='', ndiv='', space='', kforc='', layer1='', layer2='', kyndiv='', **kwargs)`

Specifies the divisions and spacing ratio on unmeshed lines.

## Parameters

**nl1**: Number of the line to be modified. If ALL, modify all selected lines ( [[lsel|LSEL]] ). If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1`.

**size**: If `NDIV` is blank, `SIZE` is the division (element edge) length. The number of divisions is automatically calculated from the line length (rounded upward to next integer). If `SIZE` is zero (or blank), use `ANGSIZ` or `NDIV`.

**angsiz**: The division arc (in degrees) spanned by the element edge (except for straight lines, which always result in one division). The number of divisions is automatically calculated from the line length (rounded upward to next integer).

**ndiv**: If positive, `NDIV` is the number of element divisions per line. If -1 (and `KFORC` = 1), `NDIV` is assumed to be zero element divisions per line. TARGE169 with a rigid specification ignores `NDIV` and will always mesh with one element division.

**space**: Spacing ratio. If positive, nominal ratio of last division size to first division size (if \> 1.0, sizes increase, if \< 1.0, sizes decrease). If negative, \| `SPACE` \| is nominal ratio of center division(s) size to end divisions size. Ratio defaults to 1.0 (uniform spacing). For layer-meshing, a value of 1.0 normally is used. If `SPACE` = FREE, ratio is determined by other considerations

**kforc**

`KFORC` 0-3 are used only with `NL1` = ALL. Specifies which selected lines are to be modified.

- `0` - Modify only selected lines having undefined (zero) divisions.
- `1` - Modify all selected lines.
- `2` - Modify only selected lines having fewer divisions (including zero) than specified with this command.
- `3` - Modify only selected lines having more divisions than specified with this command.
- `4` - Modify only nonzero settings for `SIZE`, `ANGSIZ`, `NDIV`, `SPACE`, `LAYER1`, and `LAYER2`. If `KFORC` = 4, blank or 0 settings remain unchanged.

**layer1**: Layer-meshing control parameter. Distance which defines the thickness of the inner mesh layer, `LAYER1`. Elements in this layer are uniformly-sized with edge lengths equal to the specified element size for the line (either through `SIZE` or line-length/ `NDIV` ). A positive value for `LAYER1` is interpreted as an absolute length, while a negative value in interpreted as a multiplier on the specified element size for the line. As a general rule, the resulting thickness of the inner mesh layer should be greater than or equal to the specified element size for the line. If `LAYER1` = OFF, layer-meshing control settings are cleared for the selected lines. The default value is 0.0

**layer2**: Layer-meshing control parameter. Distance which defines the thickness of the outer mesh layer, `LAYER2`. Elements in this layer transition in size from those in `LAYER1` to the global element size. A positive value of `LAYER2` is interpreted as an absolute length, while a negative value is interpreted as a mesh transition factor. A value of `LAYER2` = -2 would indicate that elements should approximately double in size as the mesh progresses normal to `LAYER1`. The default value is 0.0.

**kyndiv**

0, No, and Off means that SmartSizing cannot override specified divisions and spacing ratios. Mapped mesh fails if divisions do not match. This defines the specification as hard.

1, Yes, and On means that SmartSizing can override specified divisions and spacing ratios for curvature or proximity. Mapped meshing can override divisions to obtain required matching divisions. This defines the specification as soft.

## Notes

Defines the number of divisions and the spacing ratio on selected lines. Lines with previously specified divisions may also be changed.

This command is also valid for [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LESIZE.html
