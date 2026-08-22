---
apdl: "/CMAP"
method: cmap
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.cmap
generated: 2026-08-22
tags: [mapdl-command]
---

# /CMAP

PyMAPDL: `mapdl.cmap(fname='', ext='', kywrd='', ncntr='', **kwargs)`

Changes an existing or creates a new color mapping table.

**Command default:**

Use predefined Mechanical APDL color map table.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. If blank, restore color map.

**ext**: Filename extension (eight-character maximum).

**kywrd**

Keyword indicating the disposition of the color map file.

- `(blank)` - Loads existing color map file.
- `CREATE` - Starts the CMAP utility and modifies or creates the specified file.
- `SAVE` - Writes the active color map to the specified file, which can be imported into future sessions.

**ncntr**: Number of contours to be defined. Default = 9 (even if an existing file is being modified). Maximum = 128.

## Notes

Reads the color map file (RGB index specifications) to change from current specifications. Only one color map may be active at a time.

For 2D drivers (especially Win32c), modifying the color map can produce anomalies, including legend/contour disagreement.

When `Kywrd` equals CREATE, the 2D drivers (X11c and Win32c) display the CMAP utility with an additional contour color picker called CONTOURS. Colors selected via the CONTOURS picker affect result contour displays (such as stresses). No other drivers offer the CONTOURS picker in the CMAP utility.

Changing the color map using the **/CMAP** command changes the meaning of the color labels on the [[color|/COLOR]] command. See [[color|/COLOR]] for other color controls.

This command is valid anywhere.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMAP.html
