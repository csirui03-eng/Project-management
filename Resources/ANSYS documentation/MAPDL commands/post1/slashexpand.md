---
apdl: "/EXPAND"
method: slashexpand
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.slashexpand
generated: 2026-08-22
tags: [mapdl-command]
---

# /EXPAND

PyMAPDL: `mapdl.slashexpand(nrepeat1='', type1='', method1='', dx1='', dy1='', dz1='', nrepeat2='', type2='', method2='', dx2='', dy2='', dz2='', nrepeat3='', type3='', method3='', dx3='', dy3='', dz3='', **kwargs)`

Allows the creation of a larger graphic display than represented by the actual finite element analysis model.

## Parameters

**nrepeat1**: The number of repetitions required for the element pattern. The default is 0 (no expansion).

**type1**

The type of expansion requested.

- `RECT` - Causes a Cartesian transformation of DX, DY, and DZ for each pattern (default).
- `POLAR` - Causes a polar transformation of DR, D-Theta and DZ for each pattern.
- `AXIS` - Causes 2D axisymmetric expansion (that is, rotates a 2D model created in the X-Y plane about the Y axis to create a 3D model).
- `LRECT` - Causes a Cartesian transformation of DX, DY, and DZ for each pattern about the current local coordinate system (specified via the [[csys|CSYS]] command).
- `LPOLAR` - Causes a polar transformation of DR, D-Theta, and DZ for each pattern about the local coordinate system (specified via the [[csys|CSYS]] command).

**method1**

The method by which the pattern is repeated.

- `FULL` - Causes a normal repeat of the pattern (default).
- `HALF` - Uses a symmetry transformation for alternate repeats (to produce an image of a complete circular gear from the image of half a tooth, for example).

**dx1**, **dy1**, **dz1**: The Cartesian or polar increments between the repeated patterns. Also determines the reflection plane. Reflection is about the plane defined by the normal vector (DX, DY, DZ). If you want no translation, specify a small nonzero value. For a half-image expansion, the increment DX, DY, or DZ is doubled so that POLAR,HALF,,45 produces full images on 90° centers, and RECT,HALF,,1 produces full images on 2-meter centers.

**nrepeat2**: The number of repetitions required for the element pattern. The default is 0 (no expansion).

**type2**

The type of expansion requested.

- `RECT` - Causes a Cartesian transformation of DX, DY, and DZ for each pattern (default).
- `POLAR` - Causes a polar transformation of DR, D-Theta and DZ for each pattern.
- `AXIS` - Causes 2D axisymmetric expansion (that is, rotates a 2D model created in the X-Y plane about the Y axis to create a 3D model).
- `LRECT` - Causes a Cartesian transformation of DX, DY, and DZ for each pattern about the current local coordinate system (specified via the [[csys|CSYS]] command).
- `LPOLAR` - Causes a polar transformation of DR, D-Theta, and DZ for each pattern about the local coordinate system (specified via the [[csys|CSYS]] command).

**method2**

The method by which the pattern is repeated.

- `FULL` - Causes a normal repeat of the pattern (default).
- `HALF` - Uses a symmetry transformation for alternate repeats (to produce an image of a complete circular gear from the image of half a tooth, for example).

**dx2**, **dy2**, **dz2**: The Cartesian or polar increments between the repeated patterns. Also determines the reflection plane. Reflection is about the plane defined by the normal vector (DX, DY, DZ). If you want no translation, specify a small nonzero value. For a half-image expansion, the increment DX, DY, or DZ is doubled so that POLAR,HALF,,45 produces full images on 90° centers, and RECT,HALF,,1 produces full images on 2-meter centers.

**nrepeat3**: The number of repetitions required for the element pattern. The default is 0 (no expansion).

**type3**

The type of expansion requested.

- `RECT` - Causes a Cartesian transformation of DX, DY, and DZ for each pattern (default).
- `POLAR` - Causes a polar transformation of DR, D-Theta and DZ for each pattern.
- `AXIS` - Causes 2D axisymmetric expansion (that is, rotates a 2D model created in the X-Y plane about the Y axis to create a 3D model).
- `LRECT` - Causes a Cartesian transformation of DX, DY, and DZ for each pattern about the current local coordinate system (specified via the [[csys|CSYS]] command).
- `LPOLAR` - Causes a polar transformation of DR, D-Theta, and DZ for each pattern about the local coordinate system (specified via the [[csys|CSYS]] command).

**method3**

The method by which the pattern is repeated.

- `FULL` - Causes a normal repeat of the pattern (default).
- `HALF` - Uses a symmetry transformation for alternate repeats (to produce an image of a complete circular gear from the image of half a tooth, for example).

**dx3**, **dy3**, **dz3**: The Cartesian or polar increments between the repeated patterns. Also determines the reflection plane. Reflection is about the plane defined by the normal vector (DX, DY, DZ). If you want no translation, specify a small nonzero value. For a half-image expansion, the increment DX, DY, or DZ is doubled so that POLAR,HALF,,45 produces full images on 90° centers, and RECT,HALF,,1 produces full images on 2-meter centers.

## Notes

You can use the **/EXPAND** command to perform up to three symmetry expansions at once (that is, X, Y, and Z which is equal to going from a 1/8 model to a full model). Polar expansions allow you to expand a wheel section into a half wheel, then into the half section, and then into the whole.

The command displays elements/results when you issue the [[eplot|EPLOT]] command or postprocessing commands.

The command works on all element and result displays, except as noted below. As the graphic display is created, the elements (and results) are repeated as many times as necessary, expanding the geometry and, if necessary, the displacements and stresses.

Derived results are not supported.

The **/EXPAND** command has the following limitations:

- It does not support solid model entities.
- POLAR, FULL or HALF operations are meaningful only in global cylindrical systems and are unaffected by the [[rsys|RSYS]] or [[dsys|DSYS]] commands. Cartesian symmetry or unsymmetric operations also occur about the global Cartesian system.
- It does not average nodal results across sector boundaries, even for averaged plots (such as those obtained via the [[plnsol|PLNSOL]] command).
- Axisymmetric harmonic element results are not supported for `Type` = AXIS.

The **/EXPAND** command differs significantly from the [[expand|EXPAND]] command in several respects:

- The uses of **/EXPAND** are of a more general nature, whereas the [[expand|EXPAND]] command is intended primarily to expand modal cyclic symmetry results.
- **/EXPAND** does not change the database as does the [[expand|EXPAND]] command.
- You cannot print results displayed via **/EXPAND**.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EXPAND_sl.html
