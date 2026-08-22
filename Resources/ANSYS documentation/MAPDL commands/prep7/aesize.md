---
apdl: "AESIZE"
method: aesize
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.aesize
generated: 2026-08-22
tags: [mapdl-command]
---

# AESIZE

PyMAPDL: `mapdl.aesize(anum='', size='', **kwargs)`

Specifies the element size to be meshed onto areas.

## Parameters

**anum**: Area number of the area to which this element size specification applies. If `ANUM` = ALL, size applies to all selected areas. If `ANUM` = P, graphical picking is enabled. A component name may also be substituted for `ANUM`.

**size**: Desired element size.

## Notes

**AESIZE** allows control over the element sizing inside any area or on the face(s) of a volume.

`SIZE` controls element size on the interior of the area. For any line on the area not having its own size assignment and not controlled by keypoint size assignments, it specifies the element size along the line as well, so long as no adjacent area has a smaller size, which would take precedence. If the **AESIZE** governs the boundary and SmartSizing is on, the boundary size can be refined for curvature or proximity.

This command is also valid for [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AESIZE.html
