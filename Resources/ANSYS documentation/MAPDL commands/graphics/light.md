---
apdl: "/LIGHT"
method: light
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.light
generated: 2026-08-22
tags: [mapdl-command]
---

# /LIGHT

PyMAPDL: `mapdl.light(wn='', num='', int_='', xv='', yv='', zv='', refl='', **kwargs)`

Specifies the light direction for the display window.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**num**

Ambient or directional light key:

- `0` - Ambient light (default).
- `1` - Directional light.

**int_**: Light intensity factor (defaults to 0.3 for ambient, 1.0 for directional). This option is valid only for 3D devices).

**xv**, **yv**, **zv**: Light direction (valid only for `NUM` = 1). The directional light source is parallel to the line from point `XV`, `YV`, `ZV` to the origin, in the global Cartesian system origin. Defaults to the viewing direction ( [[view|/VIEW]] ).

**refl**: Light reflectance factor (valid only for `NUM` = 1 and 3D devices).

## Notes

Defines the light direction for the window. Use this command only with 3D graphics devices or 2D devices when Z-buffering is used ( [[slashtype|/TYPE]],,(6 or 7)). The ambient light has no direction, only an intensity. You can position the directional light source by defining a point (in the global Cartesian coordinate system) representing a point along the light directional line. This point, and the global Cartesian coordinate system origin, define the line along which the light is positioned looking toward the origin. You can use any point along the light line; for example, both (1.,1.,1.) and (2.,2.,2.) give the same light effect. For 3D graphics devices only, the directional light source also has intensity and reflectance factors.

By choosing the highest intensity ambient light for 3D graphics devices (via **/LIGHT**,WN,0,1), you can nullify color shading and other effects of directional lighting.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LIGHT.html
