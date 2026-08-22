---
apdl: "/CPLANE"
method: cplane
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.cplane
generated: 2026-08-22
tags: [mapdl-command]
---

# /CPLANE

PyMAPDL: `mapdl.cplane(key='', **kwargs)`

Specifies the cutting plane for section and capped displays.

**Command default:**

The cutting plane is normal to the viewing vector at the focus point.

## Parameters

**key**

Specifies the cutting plane:

- `0` - Cutting plane is normal to the viewing vector ( [[view|/VIEW]] ) and passes through the focus point ( [[focus|/FOCUS]] ) (default).
- `1` - The working plane ( [[wplane|WPLANE]] ) is the cutting plane.

## Notes

Defines the cutting plane to be used for section and capped displays ( [[slashtype|/TYPE]],,(1, 5, or 7)).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CPLANE.html
