---
apdl: "IMESH"
method: imesh
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.imesh
generated: 2026-08-22
tags: [mapdl-command]
---

# IMESH

PyMAPDL: `mapdl.imesh(laky='', nsla='', ntla='', kcn='', dx='', dy='', dz='', tol='', **kwargs)`

Generates nodes and interface elements along lines or areas.

## Parameters

**laky**

Copies mesh according to the following:

- `LINE or 1` - Copies line mesh (default).
- `AREA or 2` - Copies area mesh.

**nsla**: Number that identifies the source line or area. This is the line or area whose mesh will provide the pattern for the interface elements. Mechanical APDL copies the pattern of the line or area elements through the area or volume to create the mesh of area or volume interface elements.

**ntla**: Number that identifies the target line or area. This is the line or area that is opposite the source line or area specified by `NSLA`. Add `NTLA` to obtain the copied mesh from the source line or area.

**kcn**: Number that identifies the particular Mechanical APDL coordinate system.

**dx**, **dy**, **dz**: Incremental translation of node coordinates in the active coordinate system ( `DR`, `Dθ`, `DZ` for cylindrical, and `DR`, `Dθ`, `DΦ` for spherical or toroidal). The source line or area coordinates + `DX`, `DY`, `DZ` = the target line or area coordinates. If left blank, Mechanical APDL automatically estimates the incremental translation.

**tol**: Tolerance for verifying topology and geometry. By default, Mechanical APDL automatically calculates the tolerance based on associated geometries.

## Notes

Generates nodes and interface elements along lines or areas. The **IMESH** command requires that the target line or area exactly match the source line or area. Also, both target and source lines or areas must be in the same area or volume. The area or volume containing the source line or area must be meshed before executing **IMESH**, while the area or volume containing the target line or area must be meshed after executing **IMESH**.

For three dimensional problems where `LAKY` = AREA, Mechanical APDL fills the interface layer as follows:

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_IMESH.html
