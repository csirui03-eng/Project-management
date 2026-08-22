---
apdl: "/RGB"
method: rgb
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.rgb
generated: 2026-08-22
tags: [mapdl-command]
---

# /RGB

PyMAPDL: `mapdl.rgb(kywrd='', pred='', pgrn='', pblu='', n1='', n2='', ninc='', ncntr='', **kwargs)`

Specifies the RGB color values for indices and contours.

## Parameters

**kywrd**

Determines how RGB modifications will be applied.

- `INDEX` - Specifies that subsequent color values apply to Mechanical APDL color indices (0-15).
- `CNTR` - Specifies that subsequent color values apply to contours (1-128). Applies to C-option devices only (i.e. X11C or Win32C).

**pred**: Intensity of the color red, expressed as a percentage.

**pgrn**: Intensity of the color green, expressed as a percentage.

**pblu**: Intensity of the color blue, expressed as a percentage.

**n1**: First index (0-15), or contour (1-128) to which the designated RGB values apply.

**n2**: Final index (0-15), or contour (1-128) to which the designated RGB values apply.

**ninc**: The step increment between the values `N1` and `N2` determining which contours or indices will be controlled by the specified RGB values.

**ncntr**: The new maximum number of contours (1-128).

## Notes

Issuing the [[cmap|/CMAP]] command (with no filename) will restore the default color settings.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RGB.html
