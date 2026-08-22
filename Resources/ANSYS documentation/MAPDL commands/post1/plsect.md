---
apdl: "PLSECT"
method: plsect
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.plsect
generated: 2026-08-22
tags: [mapdl-command]
---

# PLSECT

PyMAPDL: `mapdl.plsect(item='', comp='', rho='', kbr='', kbr3d='', **kwargs)`

Displays membrane and membrane-plus-bending linearized stresses.

## Parameters

**item**: Label identifying the item to be processed. Valid item labels are shown in *PLSECT - Valid Item and Component Labels* below. Items also require a component label.

**comp**: Component of the item. Valid component labels are shown in *PLSECT - Valid Item and Component Labels* below.

**rho**: In-plane (X-Y) average radius of curvature of the inside and outside surfaces of an axisymmetric section. If zero (or blank), a plane or 3D structure is assumed. If nonzero, an axisymmetric structure is assumed. Use a very large number (or -1) for an axisymmetric straight section.

**kbr**

Through-thickness bending stresses key for an axisymmetric analysis ( `RHO` ≠ 0):

- `0` - Include the thickness-direction bending stresses.
- `1` - Ignore the thickness-direction bending stresses.
- `2` - Include the thickness-direction bending stress using the same formula as the Y (axial direction ) bending stress. Also use the same formula for the shear stress.

**kbr3d**

Through-thickness bending stresses key for 3D geometry ( `RHO` = 0):

- `0` - Include the thickness-direction bending stresses.
- `1` - Ignore the following thickness-direction bending stresses: SX, SXY, SXZ

## Notes

Calculates and displays the membrane and membrane-plus-bending linearized stresses (as described for the [[prsect|PRSECT]] command) along a path section ( [[path|PATH]] ) as a graph. The path section is defined by two points specified with the [[ppath|PPATH]] command. For linearized stress calculations, the path must be defined with nodes. The path must be entirely within the selected elements (that is, there must not be any element gaps along the path). The total stress (equivalent to the [[plpath|PLPATH]] display) is also displayed. This command always uses 48 divisions along the path, regardless of the number of divisions defined by [[path|PATH]].

In analyses of 3D models with `RHO` = 0, ignoring the calculated out-of-plane bending stresses is recommended in some scenarios when determining the linearized bending stresses. If `KBR3D` = 0, all calculated stresses are included in the linearized bending-stress calculations. If `KBR3D` = 1, these calculated out-of-plane bending stresses are ignored in the linearized bending-stress calculations: SX, SXY, SXZ. (The principal bending-stress calculation for S1, S2, S3, SINT, and SEQV is performed with these zeroed components.)

Portions of this command are not supported by PowerGraphics ( [[graphics|/GRAPHICS]],POWER).

### PLSECT - Valid Item and Component Labels

| Item | Comp | Description |
|----|----|----|
| Valid item and component labels for element results are: |  |  |
| S | X, Y, Z, XY, YZ, XZ | Component stress. |
| " | 1, 2, 3 | Principal stress. |
| " | INT, EQV | Stress intensity or equivalent stress. |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLSECT.html
