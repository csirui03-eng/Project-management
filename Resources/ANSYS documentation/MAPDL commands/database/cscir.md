---
apdl: "CSCIR"
method: cscir
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.coordinate_system.CoordinateSystem.cscir
generated: 2026-08-22
tags: [mapdl-command]
---

# CSCIR

PyMAPDL: `mapdl.cscir(kcn='', kthet='', kphi='', **kwargs)`

Locates the singularity for non-Cartesian local coordinate systems.

**Command default:**

Singularities at ±180°.

## Parameters

**kcn**: Number of the local coordinate system in which singularity location is to be changed. Must be greater than 10.

**kthet**

Theta singularity location for cylindrical, spherical, and toroidal systems:

- `0` - Singularity at ±180°.
- `1` - Singularity at 0° (360°).

**kphi**

Phi singularity location for toroidal systems:

- `0` - Singularity in phi direction at ±180°.
- `1` - Singularity in phi direction at 0° (360°).

## Notes

Continuous closed surfaces (circles, cylinders, spheres, etc.) have a singularity (discontinuity) at θ = ±180°. For local cylindrical, spherical, and toroidal coordinate systems, this singularity location may be changed to 0° (360°).

An additional, similar singularity occurs in the toroidal coordinate system at Φ = ±180° and can be moved with `KPHI`. Additional singularities occur in the spherical coordinate system at Φ = ±90°, but cannot be moved.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CSCIR.html
