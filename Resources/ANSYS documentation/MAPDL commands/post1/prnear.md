---
apdl: "PRNEAR"
method: prnear
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.prnear
generated: 2026-08-22
tags: [mapdl-command]
---

# PRNEAR

PyMAPDL: `mapdl.prnear(lab='', opt='', kcn='', val1='', val2='', val3='', val4='', val5='', val6='', val7='', val8='', val9='', **kwargs)`

Prints the pressure in the near zone exterior to the equivalent source surface.

## Parameters

**lab**

Print the maximum pressure or sound pressure level:

- `POINT` - at the point (x,y,z)
- `SPHERE` - on the spherical structure
- `PATH` - along the path

**opt**

- `PSUM` - Maximum complex pressure for acoustics.
- `PHAS` - Phase angle of complex pressure for acoustics.
- `SPL` - Sound pressure level for acoustics.
- `SPLA` - A-weighted sound pressure level for acoustics (dBA).

**kcn**: KCN is the coordinate system reference number. It may be 0 (Cartesian) or any previously defined local coordinate system number (\>10). Defaults to 0.

**val1**, **val2**, **val3**, **val4**, **val5**, **val6**, **val7**, **val8**, **val9**

For `Lab` = POINT:

- `VAL1` - x coordinate value
- `VAL2` - y coordinate value
- `VAL3` - z coordinate value
- `VAL4 -, VAL8` - not used
- `VAL9` - Thickness of model in z direction (defaults to 0).

For `LAB` = SPHERE:

- `VAL1` - Radius of spherical surface in spherical coordinate system.
- `VAL2` - Starting φ angle (degree) in the spherical coordinate system. Defaults to 0.
- `VAL3` - Ending φ angle (degree) in the spherical coordinate system. Defaults to 0.
- `VAL4` - Number of divisions between the starting and ending φ angles for data computations. Defaults to 0.
- `VAL5` - Starting θ angle (degrees) in the spherical coordinate system. Defaults to 0 in 3D and 90 in 2D extension.
- `VAL6` - Ending θ angle (degrees) in the spherical coordinate system. Defaults to 0 in 3D and 90 in 2D extension.
- `VAL7` - Number of divisions between the starting and ending θ angles for data computations. Defaults to 0.
- `VAL8` - Reference rms sound pressure. Defaults to 2x10 <sup>-5</sup> Pa.
- `VAL9` - Thickness of 2D model extension in z direction (defaults to 0).

For `Lab` = [[path|PATH]], **PRNEAR** computes the pressure for the path data points for the path currently defined by the [[path|PATH]] and [[ppath|PPATH]] commands.

## Notes

The command uses the equivalent source principle to calculate the pressure in the near zone exterior to the equivalent source surface (flagged with the Maxwell surface flag in the preprocessor) for one of the following locations:

- A point X, Y, Z in the KCN coordinate system
- A spherical surface in the KCN coordinate system
- A path defined by the [[path|PATH]] and [[ppath|PPATH]] commands

To list the pressure results for a path, use the [[prpath|PRPATH]] command. See [[hfsym|HFSYM]] command for the model symmetry.

To retrieve saved equivalent source data, issue the [[set|SET]], `Lstep`, `Sbstep`,,REAL command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRNEAR.html
