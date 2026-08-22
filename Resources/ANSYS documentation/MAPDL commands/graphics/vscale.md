---
apdl: "/VSCALE"
method: vscale
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.scaling.Scaling.vscale
generated: 2026-08-22
tags: [mapdl-command]
---

# /VSCALE

PyMAPDL: `mapdl.vscale(wn='', vratio='', key='', **kwargs)`

Scales the length of displayed vectors.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**vratio**: Ratio value applied to the automatically calculated scale factor (defaults to 1.0, that is, use scale factor as automatically calculated).

**key**

Relative scaling key:

- `0` - Use relative length scaling among vectors based on magnitudes.
- `1` - Use uniform length scaling for all vector lengths.

## Notes

Allows scaling of the vector length displayed with the [[plvect|PLVECT]] command of POST1 and the [[pbc|/PBC]] and [[psf|/PSF]] commands. Also allows the scaling of the element (that is, [[psymb|/PSYMB]] ,ESYS) and the nodal (that is, [[psymb|/PSYMB]],NDIR) coordinate system symbols.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VSCALE.html
