---
apdl: "MSHCOPY"
method: mshcopy
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.mshcopy
generated: 2026-08-22
tags: [mapdl-command]
---

# MSHCOPY

PyMAPDL: `mapdl.mshcopy(keyla='', laptrn='', lacopy='', kcn='', dx='', dy='', dz='', tol='', low='', high='', **kwargs)`

Simplifies the generation of meshes that have matching node element patterns on two different line groups (in 2D) or area groups (3D).

## Parameters

**keyla**: Copy line mesh (default) if LINE, 0 or 1. Copy area mesh if AREA, or 2.

**laptrn**: Meshed line/area to be copied, or a component name containing a list. If `LAPTRN` = P, graphical picking is enabled (valid only in the GUI).

**lacopy**: Unmeshed line/area to get copied mesh, or a component name containing a list. If `LACOPY` = P, graphical picking is enabled (valid only in the GUI).

**kcn**: In coordinate system `KCN`, `LAPTRN` + `DX` `DY` `DZ` = `LACOPY`.

**dx**, **dy**, **dz**: Node location increments in the active coordinate system (DR, Dθ, DZ for cylindrical, DR, Dθ, DΦ for spherical or toroidal).

**tol**: Tolerance. Defaults to 1.e-4.

**low**: Name of low node component to be defined (optional).

**high**: Name of high node component to be defined (optional).

## Notes

Matching meshes are used for rotational (cyclic) symmetry, or for contact analysis using coupling or node-to-node gap elements. See [Using CPCYC and MSHCOPY Commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_8.html#) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for more information.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MSHCOPY.html
