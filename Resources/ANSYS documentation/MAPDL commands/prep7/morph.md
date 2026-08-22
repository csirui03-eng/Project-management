---
apdl: "MORPH"
method: morph
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.morphing.Morphing.morph
generated: 2026-08-22
tags: [mapdl-command]
---

# MORPH

PyMAPDL: `mapdl.morph(option='', remeshopt='', elemset='', armax='', voch='', arch='', step='', time='', stropt='', **kwargs)`

Specifies morphing and remeshing controls.

## Parameters

**option**

- `OFF` - Turns off morphing for field elements (default).
- `ON` - Turns on morphing for field elements.

**remeshopt**

- `OFF` - Do not remesh (default).
- `ON` - Remesh when element qualities fall below values specified by `ARMAX`, `VOCH`, or `ARCH` as explained below. Valid only when `Option` is ON.

**elemset**

- `ALL` - Remesh all selected elements if the quality of the worst defined element falls below any quality requirement (default when `Remeshopt` = ON).
- `CompName` - Specify a component name, up to 256 characters. All elements included in this component name are remeshed if the quality of the worst element falls below any quality requirement.

**armax**: The maximum allowable element generalized aspect ratio. Defaults to 5.

**voch**: The maximum allowable change of element size (area or volume). Defaults to 3.

**arch**: The maximum allowable element aspect ratio change. Defaults to 3.

**step**: The frequency of element quality checking, based on time steps. A quality check takes place at the intervals defined by `STEP`. Defaults to 1 (quality check at every step).

**time**: A quality check takes place at the time point specified. Defaults to -1 (a quality check at every time point).

**stropt**

- `NO` - There are no structural elements in the model (default).
- `YES` - There are structural elements in the model and the morphing happens after the structural solution.

## Notes

**MORPH** is applicable to any non-structural field analysis. It activates displacement degrees of freedom for non-structural elements so that boundary conditions may be placed on the field mesh to constrain the movement of the non-structural mesh during morphing. It morphs the non-structural mesh using displacements transferred at the surface interface between the structural field and the non-structural field. The displacements of non-structural elements are mesh displacements to avoid mesh distortion, but have no physical meaning except at the interface. **MORPH** does not support surface, link, or shell elements, or any element shape other than triangles, quads, tets, and bricks. Morphed fields must be in the global Cartesian system ( [[csys|CSYS]] = 0).

If `StrOpt` = YES, the following non-structural element types will be morphed:

- Acoustic: `FLUID30`, `FLUID220`, `FLUID221`, `FLUID243`, `FLUID244`,
- Electrostatic `PLANE121`, `SOLID122`, and `SOLID123`,
- Electric `PLANE230`, `SOLID231`, and `SOLID232`,
- Electromagnetic `PLANE233`, `SOLID236`, and `SOLID237`,
- Thermal `PLANE35`, `PLANE55`, `PLANE77`, `PLANE292`, `PLANE293`, `SOLID70`, `SOLID87`, `SOLID90`, `SOLID278`, `SOLID279`, and `SOLID291`,
- Diffusion `PLANE238`, `SOLID239`, and `SOLID240`,
- Coupled-field `PLANE222`, `PLANE223`, `SOLID225`, `SOLID226`, and `SOLID227` with no structural degrees of freedom.

The following structural elements types are supported by `StrOpt` = YES:

- `PLANE182`, `PLANE183`, `SOLID185`, `SOLID186`, `SOLID187`, `SOLSH190`,
- Coupled-field `PLANE222`, `PLANE223`, `SOLID225`, `SOLID226`, and `SOLID227` with structural degrees of freedom.

After each remesh, new databases and results files are written with the extensions `.rth0n` and `.db0n`, where `n` is the remesh file number ( `FieldName.rth01`, `FieldName.rth02`,... and `FieldName.db01`, `FieldName.db02`, etc.). The original database file is `FieldName.dbo`. The `FieldName.db01`, `FieldName.db02`, etc. files have elements that are detached from the solid model.

Remeshing has the following restrictions:

- Valid only for the electrostatic elements ( `PLANE121`, `SOLID122`, and `SOLID123` )
- Limited to triangle (2D) and tetrahedral (3D) options of these elements
- No body loads allowed in the interior nodes of the remeshing domain
- Nodes on the boundary cannot be remeshed; remeshing will not work if morphing failed on the surface nodes
- Not suitable for extreme area or volume changes

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MORPH.html
