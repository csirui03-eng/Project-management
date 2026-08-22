---
apdl: "/PLOPTS"
method: plopts
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.plopts
generated: 2026-08-22
tags: [mapdl-command]
---

# /PLOPTS

PyMAPDL: `mapdl.plopts(label='', key='', **kwargs)`

Controls graphics options on subsequent displays.

**Command default:**

See individual label defaults.

The Multi-legend mode ( **/PLOPTS**,INFO,3) is the default for contour legend displays.

## Parameters

**label**

Apply display items as selected from the following labels:

- `INFO` - Controls the display of the legend (ON or OFF) and allows the choice of preset or Multi-legend placement. Control is provided by the `KEY` values. (Defaults to `KEY` =3 when the GUI is on. Defaults to `KEY` = 2 otherwise.)
- `LEG1` - Header portion of legend column (defaults to ON).
- `LEG2` - View portion of legend column (defaults to ON (except off with contour displays)).
- `LEG3` - View the contour section of the legend column (defaults to ON).
- `FRAME` - Frame border lines around windows (defaults to ON).
- `TITLE` - Title (bottom left text) (defaults to ON).
- `MINM` - Min-Max symbols on contour displays (defaults to ON).
- `LOGO` - Ansys logo (defaults to OFF (displayed as text at top of legend column)). If `KEY` = ON, the text is removed from legend column but the logo symbol is displayed in whichever active window is either in the uppermost right corner and on top, or if there is no window in that location, then in the window to the furthest right of the screen. Version information remains in the legend column.
- `WINS` - Controls whether graphics windows automatically stretch or shrink to adjust to screen size as the legend column is turned off or on ( **/PLOPTS**,INFO) (defaults to ON). If WINS is on and the legend column is changed from off to on, all windows are shrunk regardless of what their correct size is.
- `WP` - Working plane (defaults to OFF). The working plane is drawn as part of the display ( not just an overlaid image as in [[wpstyl|WPSTYL]] ). This option is best used in combination with a hidden- line technique ( [[slashtype|/TYPE]] ).
- `DATE` - Controls the display of the date and time in your legend. Subsequent `KEY` values control the display as follows:
  - 0 - No date or time displays are included in your legend.
  - 1 - Only the date is shown.
  - 2 - Both the date and time are shown (default).
- `FILE` - Controls the display of the Mechanical APDL jobname in your legend. Subsequent `KEY` values control the display as follows:
  - 0 - The Mechanical APDL jobname is not included in your legend (default).
  - 1 - The Mechanical APDL jobname is included in your legend.

**key**

Switch:

- `OFF or 0` - Do not apply this display item. For `Label` = DATE, no time or date are displayed.
- `ON or 1` - Apply this display item. For `Label` = DATE, show only the date.
- `AUTO or 2` - For `Label` = INFO, initiate Auto-legend mode. If the display has contours, the legend is ON; if the display has no contours, the legend is OFF. For `Label` = DATE, display both the date and time.
- `3` - For `Label` = INFO, switch to Multi-legend mode. See the [[udoc|/UDOC]] command for the available legend configurations.

## Notes

Use **/PLOPTS**,STAT to display settings. Use **/PLOPTS**,DEFA to reset all specifications back to their defaults.

When you perform multiple results displays, contours on the legend column may be truncated. To avoid this, specify **/PLOPTS**,LEG1,0.

The Multi-legend mode provides a number of legend data item priority and placement options. These options are accessed via the GUI at Utility Menu\> PlotCtrls\> Window Controls\> Window Options. The [[udoc|/UDOC]] command provides command line o ptions for this capability.

This command is valid in any processor.

This command is not available for Academic Research or Teaching level products

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLOPTS.html
