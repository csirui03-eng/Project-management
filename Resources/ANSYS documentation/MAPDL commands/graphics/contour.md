---
apdl: "/CONTOUR"
method: contour
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.contour
generated: 2026-08-22
tags: [mapdl-command]
---

# /CONTOUR

PyMAPDL: `mapdl.contour(wn='', ncont='', vmin='', vinc='', vmax='', **kwargs)`

Specifies the uniform contour values on stress displays.

**Command default:**

Nine contour values uniformly spaced between the extreme values, or no contours if the ratio of range to minimum value (or range to maximum if minimum = 0) is less than 0.001.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**ncont**: Number of contour values. `NCONT` defaults to 9 for X11 or WIN32 and to 128 for X11c or WIN32C. The default graphics window display for 3D devices is a smooth continuous shading effect that spans the maximum of 128 contours available. Use the [[dv3d|/DV3D]] command to create defined banding for your contour values (values of 9 and 128 are displayed in smooth shading only). The legend, however, will display only nine color boxes, which span the full range of colors displayed in the graphics window.

**vmin**: Minimum contour value. If `VMIN` = AUTO, automatically calculate contour values based upon `NCONT` uniformly spaced values over the min-max extreme range. Or, if `VMIN` = USER, set contour values to those of the last display (useful when last display automatically calculated contours).

**vinc**: Value increment (positive) between contour values. Defaults to ( `VMAX` - `VMIN` ) `/NCONT`.

**vmax**: Maximum contour value. Ignored if both `VMIN` and `VINC` are specified.

## Notes

Values represent contour lines in vector mode, and the algebraic maximum of contour bands in raster mode.

Regardless of how many contours ( `NCONT` ) are specified, the actual number of contours appearing on your display depends also on the device name, whether the display is directed to the screen or to a file, the display mode (vector or raster), and the number of color planes. (All of those items are controlled via [[show|/SHOW]].) In any case, regardless of whether they are smoothed or banded, only 128 contours can be displayed.

For more information about changing the number of contours, see [Creating Geometric Results Displays](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS12_6.html).

When the current Mechanical APDL graphics are not displayed as Multi-Plots:

- If the current device is a 3D device ( [[show|/SHOW]],3D), the model contours in all active windows are the same, even if separate **/CONTOUR** commands are issued for each active window.

\* Mechanical APDL maintains a single data structure (segment) containing one set of contours. The program displays the same segment in all windows. The view settings of each window constitute the only differences in the contour plots in the active windows.

This command is valid in any processor.

For alternate specifications, see [[cval|/CVAL]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CONTOUR.html
