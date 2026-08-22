---
apdl: "ASBA"
method: asba
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.asba
generated: 2026-08-22
tags: [mapdl-command]
---

# ASBA

PyMAPDL: `mapdl.asba(na1='', na2='', sepo='', keep1='', keep2='', **kwargs)`

Subtracts areas from areas.

## Parameters

**na1**: Area (or areas, if picking is used) to be subtracted from. If ALL, use all selected areas. Areas specified in this argument are not available for use in the `NA2` argument. If P, graphical picking is enabled (valid only in the GUI) and remaining fields are ignored. A component name may also be substituted for `NA1`.

**na2**: Area (or areas, if picking is used) to subtract. If ALL, use all selected areas (except those included in the `NA1` argument). A component name may also be substituted for `NA2`.

**sepo**

Behavior if the intersection of the `NA1` areas and the `NA2` areas is a line or lines:

- `(blank)` - The resulting areas will share line(s) where they touch.
- `SEPO` - The resulting areas will have separate, but coincident line(s) where they touch.

**keep1**

Specifies whether `NA1` areas are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NA1` areas after **ASBA** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NA1` areas after **ASBA** operation (override [[boptn|BOPTN]] command settings).

**keep2**

Specifies whether `NA2` areas are to be deleted:

- `(blank)` - Use the setting of KEEP on the [[boptn|BOPTN]] command.
- `DELETE` - Delete `NA2` areas after **ASBA** operation (override [[boptn|BOPTN]] command settings).
- `KEEP` - Keep `NA2` areas after **ASBA** operation (override [[boptn|BOPTN]] command settings).

## Returns

`int`: Area number of the new area (if applicable)

## Notes

Generates new areas by subtracting the regions common to both `NA1` and `NA2` areas (the intersection) from the `NA1` areas. The intersection can be an area(s) or line(s). If the intersection is a line and `SEPO` is blank, the `NA1` area is divided at the line and the resulting areas will be connected, sharing a common line where they touch. If `SEPO` is set to SEPO, `NA1` is divided into two unconnected areas with separate lines where they touch. See [Solid Modeling](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD5_10.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated. **ASBA**,ALL,ALL will have no effect since all the areas (in `NA1` ) will be unavailable as `NA2` areas.

## Examples

Subtract a 0.5 x 0.5 rectangle from a 1 x 1 rectangle.

``` python
>>> anum0 = mapdl.blc4(0, 0, 1, 1)
>>> anum1 = mapdl.blc4(0.25, 0.25, 0.5, 0.5)
>>> aout = mapdl.asba(anum0, anum1)
>>> aout
3
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ASBA.html
