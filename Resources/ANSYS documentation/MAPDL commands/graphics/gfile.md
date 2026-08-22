---
apdl: "/GFILE"
method: gfile
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.gfile
generated: 2026-08-22
tags: [mapdl-command]
---

# /GFILE

PyMAPDL: `mapdl.gfile(size='', **kwargs)`

Specifies the pixel resolution on Z-buffered graphics files.

## Parameters

**size**: Pixel resolution. Defaults to a pixel resolution of 800. Valid values are from 256 to 2400.

## Notes

Defines the pixel resolution on subsequently written graphics files (for example, JPEG, PNG, TIFF) for software Z-buffered displays ( [[slashtype|/TYPE]] ). Lowering the pixel resolution produces a fuzzier image; increasing the resolution produces a sharper image but takes a little longer.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GFILE.html
