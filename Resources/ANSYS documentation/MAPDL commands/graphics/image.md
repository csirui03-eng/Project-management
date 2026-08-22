---
apdl: "/IMAGE"
method: image
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.image
generated: 2026-08-22
tags: [mapdl-command]
---

# /IMAGE

PyMAPDL: `mapdl.image(label='', fname='', ext='', **kwargs)`

Allows graphics data to be captured and saved.

## Parameters

**label**

Label specifying the operation to be performed:

- `CAPTURE` - Capture the image from the graphics window to a new window.
- `RESTORE` - Restore the image from a file to a new window.
- `SAVE` - Save the contents of the graphic window to a file.
- `DELETE` - Delete the window that contains the file.

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name.

**ext**: Filename extension (eight-character maximum). If no extension is specified, `bmp` will be used on Windows systems, and `img` will be used on Linux systems.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_IMAGE.html
