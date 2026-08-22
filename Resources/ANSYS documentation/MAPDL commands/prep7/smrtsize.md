---
apdl: "SMRTSIZE"
method: smrtsize
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.smrtsize
generated: 2026-08-22
tags: [mapdl-command]
---

# SMRTSIZE

PyMAPDL: `mapdl.smrtsize(sizlvl='', fac='', expnd='', trans='', angl='', angh='', gratio='', smhlc='', smanc='', mxitr='', sprx='', **kwargs)`

Specifies meshing parameters for automatic (smart) element sizing.

## Parameters

**sizlvl**

Overall element size level for meshing. The level value controls the fineness of the mesh. (Any input in this field causes remaining arguments to be ignored.) Valid inputs are:

- `n` - Activate SmartSizing and set the size level to `n`. Must be an integer value from 1 (fine mesh) to 10 (coarse mesh). Remaining arguments are ignored, and argument values are set as shown in *SMRTSIZE - Argument Values for h-elements*.
- `STAT` - List current **SMRTSIZE** settings.
- `DEFA` - Set all **SMRTSIZE** settings to default values (as shown in *SMRTSIZE - Argument Values for h-elements* for size level 6).
- `OFF` - Deactivate SmartSizing. Current settings of [[desize|DESIZE]] will be used. To reactivate SmartSizing, issue **SMRTSIZE**, `n`.

**fac**: Scaling factor applied to the computed default mesh sizing. Defaults to 1 for h-elements (size level 6), which is medium. Values from 0.2 to 5.0 are allowed.

**expnd**: Mesh expansion (or contraction) factor. (This factor is the same as [[mopt|MOPT]],EXPND, `Value`.) `EXPND` is used to size internal elements in an area based on the size of the elements on the area's boundaries. For example, issuing **SMRTSIZE**,,,2 before meshing an area will allow a mesh with elements that are approximately twice as large in the interior of an area as they are on the boundary. If `EXPND` is less than 1, a mesh with smaller elements on the interior of the area will be allowed. `EXPND` should be greater than 0.5 but less than 4. `EXPND` defaults to 1 for h-elements (size level 6), which does not allow expansion or contraction of internal element sizes (except when using [[aesize|AESIZE]] element sizing). (If `EXPND` is set to zero, the default value of 1 will be used.) The actual size of the internal elements will also depend on the `TRANS` option or upon [[aesize|AESIZE]] or [[esize|ESIZE]] sizing, if used.

**trans**: Mesh transition factor. (This factor is the same as [[mopt|MOPT]],TRANS, `Value`.) `TRANS` is used to control how rapidly elements are permitted to change in size from the boundary to the interior of an area. `TRANS` defaults to 2.0 for h-elements (size level 6), which permits elements to approximately double in size from one element to the next as they approach the interior of the area. (If `TRANS` is set to zero, the default value will be used.) `TRANS` must be greater than 1 and, for best results, should be less than 4. The actual size of the internal elements will also depend on the `EXPND` option or upon [[aesize|AESIZE]] or [[esize|ESIZE]] sizing, if used.

**angl**: Maximum spanned angle per lower-order element for curved lines. Defaults to 22.5 degrees per element (size level 6). This angle limit may be exceeded if the mesher encounters a small feature (hole, fillet, etc.). (This value is not the same as that set by [[desize|DESIZE]],,, `ANGL`.)

**angh**: Maximum spanned angle per higher-order element for curved lines. Defaults to 30 degrees per element (size level 6). This angle limit may be exceeded if the mesher encounters a small feature (hole, fillet, etc.). (This value is NOT the same as that set by [[desize|DESIZE]],,,, `ANGH`.)

**gratio**: Allowable growth ratio used for proximity checking. Defaults to 1.5 for h-elements (size level 6). Values from 1.2 to 5.0 are allowed; however, values from 1.5 to 2.0 are recommended.

**smhlc**: Small hole coarsening key, can be ON (default for size level 6) or OFF. If ON, this feature suppresses curvature refinement that would result in very small element edges (that is, refinement around small features).

**smanc**: Small angle coarsening key, can be ON (default for all levels) or OFF. If ON, this feature restricts proximity refinement in areas where it is ill-advised (that is, in tight corners on areas, especially those that approach 0 degrees).

**mxitr**: Maximum number of sizing iterations (defaults to 4 for all levels).

**sprx**: Surface proximity refinement key, can be off ( `SPRX` = 0, which is the default for all levels ) or on via two different values ( `SPRX` = 1 or `SPRX` = 2). If `SPRX` = 1, surface proximity refinement is performed and any shell elements that need to be modified are modified. If `SPRX` =2, surface proximity refinement is performed but no shell elements are altered.

## Notes

If a valid level number (1 (fine) to 10 (coarse)) is input on `SIZLVL`, inputs for remaining arguments are ignored, and the argument values are set as shown in *SMRTSIZE - Argument Values for h-elements*.

The settings shown are for h-elements. The first column contains `SIZLV` data, ranging from 10 (coarse) to 1 (fine). The default is 6 (indicated by the shaded row).

### SMRTSIZE - Argument Values for h-elements

|  | FAC | EXPND | TRANS | ANGL | ANGH | GRATIO | SMHLC | SMANC | MXITR | SPRX |
|----|----|----|----|----|----|----|----|----|----|----|
| 10 | 5.0 | 2.0 | 2.0\* | 45.0 | 45.0\* | 2.0 | on | on | 4\* | off |
| 9 | 3.0 | 1.75 | 2.0\* | 36.0 | 45.0\* | 1.9 | on | on | 4\* | off |
| 8 | 1.875 | 1.5 | 2.0\* | 30.0 | 45.0\* | 1.8 | on | on | 4\* | off |
| 7 | 1.5 | 1.0 | 2.0\* | 26.0 | 36.0\* | 1.7 | on | on | 4\* | off |
| 6 | 1.0\* | cellfont Shading="gray1" ? 1.0\* | 2.0\* | 22.5 | 30.0\* | cellfont Shading="gray1" ? 1.5\* | on | on | 4\* | cellfont Shading="gray1" ? off |
| 5 | 0.65 | 1.0\* | 2.0\* | 18.0 | 27.0 | 1.5 | on | on | 4\* | off |
| 4 | 0.4 | 1.0\* | 2.0\* | 15.0 | 22.0 | 1.5 | off | on | 4\* | off |
| 3 | 0.3 | 1.0\* | 2.0\* | 12.0 | 18.0 | 1.5 | off | on | 4\* | off |
| 2 | 0.25 | 1.0\* | 2.0\* | 10.0 | 15.0 | 1.5 | off | on | 4\* | off |
| 1 | 0.2 | 1.0\* | 2.0\* | 7.5 | 15.0 | 1.4 | off | on | 4\* | off |

Where appropriate, SmartSizing will start with [[aesize|AESIZE]] settings. Elsewhere, it will start with any defined [[esize|ESIZE]],SIZE setting. It will locally override [[aesize|AESIZE]] or [[esize|ESIZE]] for proximity and curvature. SmartSizing ignores any [[esize|ESIZE]],,NDIV setting.

[[lesize|LESIZE]] line division and spacing specifications will be honored by SmartSizing, unless you give permission for SmartSizing to override them (for proximity or curvature) by setting KYNDIV to 1. Lines not having an [[lesize|LESIZE]] specification are meshed as well as they can be.

This command is also valid for [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SMRTSIZE.html
