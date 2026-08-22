---
apdl: "/TRLCY"
method: trlcy
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.trlcy
generated: 2026-08-22
tags: [mapdl-command]
---

# /TRLCY

PyMAPDL: `mapdl.trlcy(lab='', tlevel='', n1='', n2='', ninc='', **kwargs)`

Specifies the level of translucency.

## Parameters

**lab**

Apply translucency level to the items specified by the following labels:

- `ELEM` - Elements. Use `N1`, `N2`, `NINC` fields for element numbers.
- `AREA` - Solid model areas. Use `N1`, `N2`, `NINC` fields for area numbers.
- `VOLU` - Solid model volumes. Use `N1`, `N2`, `NINC` fields for volume numbers.
- `ISURF` - Isosurfaces (surfaces of constant stress, etc., value). Translucency varies with result value, to a maximum of the specified translucency level.
- `CM` - Component group. Use `N1` for component name, ignore `N2` and `NINC`.
- `CURVE` - Filled areas under curves of line graphs. Use `N1`, `N2`, `NINC` fields for curve numbers.
- `ZCAP` - If [[slashtype|/TYPE]], `WN`,ZCAP is the current display type, then **/TRLCY**,ZCAP, `TLEVEL` will display the model in window `WN` with the portion of the model in front of the section plane displayed at the translucency level `TLEVEL`.
- `ON, OFF` - Sets the specified translucency display on or off. All other fields are ignored.

**tlevel**: Translucency level: 0.0 (opaque) to 1.0 (transparent).

**n1**, **n2**, **ninc**: Used only with labels as noted above. Apply translucency level to `Lab` items numbered `N1` to `N2` (defaults to `N1` ) in steps of `NINC` (defaults to 1). If `N1` is blank or ALL, apply specified translucency level to entire selected range. If `Lab` is CM, use component name for `N1` and ignore `N2` and `NINC`. A value of `N1` = P allows you to graphically pick elements, areas, and volumes. You can then assign translucency levels to the entities via the picker. The `Lab` and `TLEVEL` fields are ignored when translucency is applied by picking.

## Notes

Specifies the level of translucency for various items. Issue **/TRLCY**,DEFA to reset the default (0) translucency levels. This command is valid only on selected 2D and 3D graphics devices; see filename="Hlp_G_BAS11_3.html"? in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for more information on applying translucency.

For 2D devices, the program displays only the visible faces of the items being displayed. The information behind the facing planes is not displayed. Issuing the [[shrink|/SHRINK]] command will force the hardware to display information behind the translucent items.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TRLCY.html
