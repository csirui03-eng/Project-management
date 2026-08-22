---
apdl: "AREMESH"
method: aremesh
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.rezoning.Rezoning.aremesh
generated: 2026-08-22
tags: [mapdl-command]
---

# AREMESH

PyMAPDL: `mapdl.aremesh(lcomb='', angle='', **kwargs)`

Generates an area in which to create a new mesh for rezoning.

## Parameters

**lcomb**

Specifies how to combine adjacent line segments:

- `0` - Line segments combined by connecting ends to ends. This value is the default.
- `-1` - No line segments combined.

**angle**: The maximum angle (in degrees) allowed for connecting two line segments together. The default value is 30. This value is valid only when `LCOMB` = 0.

## Notes

Issue the **AREMESH** command after issuing a [[remesh|REMESH]],START command and before issuing a [[remesh|REMESH]],FINISH command.

The **AREMESH** command cannot account for an open area (or "hole") inside a completely enclosed region. Instead, try meshing around an open area by selecting two adjoining regions; for more information, see.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AREMESH.html
