---
apdl: "/SHOW"
method: show
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.show
generated: 2026-08-22
tags: [mapdl-command]
---

# /SHOW

PyMAPDL: `mapdl.show(fname='', option='', vect='', ncpl='', **kwargs)`

Specifies the device and other parameters for graphics displays.

## Parameters

**fname**

Device name, file name, or keyword, as listed below:

- `<, device name >` - Any valid graphics display device name (for example, X11, 3D etc.). Defaults to X11 for most systems. See [Getting Started with Graphics](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS8_7.html) in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for details. A device name must be defined before activating the Graphical User Interface (GUI). Once the GUI is activated, the device name cannot be changed for that session, except for switching between X11 and X11C.
- `TERM` - Graphics displays are switched back to the last-specified device name.
- `CLOSE` - This option purges the graphics file buffer. The CLOSE option should be issued any time you are changing graphics devices or file output types during a session. Graphics displays are switched back to the last-specified device name, and any open graphics files are closed. The CLOSE option is similar to the TERM option, however, with the CLOSE option, another process can access the data in the graphics file. The CLOSE option causes graphics file buffers to be flushed to the graphics file.
- `OFF` - Graphics display requests are ignored.
- `(blank)` - If blank in interactive mode, graphics will be displayed on screen as requested by display commands (no file written).
- `JPEG` - Creates JPEG files that are named `Jobnamennn.jpg`, where `nnn` is a numeric value that is incremented by one as each additional file is created; that is, `Jobname000.jpg`, `Jobname001.jpg`, `Jobname002.jpg`, and so on. Ignores the `Ext` field.
- `TIFF` - Creates tagged image format files that are named `Jobnamennn.tif`, where `nnn` is a numeric value that is incremented by one as each additional file is created; that is, `Jobname000.tif`, `Jobname001.tif`, `Jobname002.tif`, and so on. This value for the `Fname` argument ignores the `Ext` field. (See the [[tiff|TIFF]] command for options.)
- `PNG` - Creates PNG (Portable Network Graphics) files that are named `Jobnamennn.png`, where `nnn` is a numeric value that is incremented by one as each additional file is created; that is, `Jobname000.png`, `Jobname001.png`, `Jobname002.png`, and so on. This value for the `Fname` argument ignores the `Ext` field. (See the [[pngr|PNGR]] command for options.)
- `VRML` - Creates Virtual Reality Meta Language files named `Jobname000.wrl` that can be displayed on 3D Internet web browsers. Ignores the `Ext` and `NCPL` fields.

**option**

Assign a file name extension or specify reverse video output:

- `Ext` - File name extension (eight-character maximum).
- `REV` - Reverse background/image (black/white) colors. Valid with `Fname` = PNG (recommended), JPEG, and TIFF. This option is ignored if a previously specified color map table ( [[cmap|/CMAP]] or [[rgb|/RGB]] ) is in effect.

**vect**

Specifies raster or vector display mode. This affects area, volume, and element displays, as well as geometric results displays such as contour plots. See the [[device|/DEVICE]] command for an alternate way to toggle between raster and vector mode. Changing `VECT` also resets the [[slashtype|/TYPE]] command to its default.

- `0` - Raster display (color filled entities; default)
- `1` - Vector display (outlined entities; that is, "wireframe")

**ncpl**: Sets the number of color planes (4 to 8). Default is device-dependent. `NCPL` is not supported by all graphics devices.

## Notes

Specifies the device to be used for graphics displays, and specifies other graphics display parameters. Display may be shown at the time of generation (for interactive runs at a graphics display terminal) or diverted to a file. Issue [[pstatus|/PSTATUS]] for display status.

Batch runs do not have access to the fonts available on your system. The Courier and Helvetica font files used for JPEG, PNG and TIFF batch output are copyrighted by Adobe Systems Inc. and Digital Equipment Corp. Permission to use these trademarks is hereby granted only in association with the images described above. Batch run JPEG output is produced at the default quality index value of 75, unless specified otherwise.

Interactive displays default to eight color planes ( `NCPL` = 8) for most monitors, while graph file output defaults to eight color planes for VRML output, and four color planes for JPEG, PNG, and TIFF.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SHOW.html
