---
apdl: "FSSECT"
method: fssect
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.fssect
generated: 2026-08-22
tags: [mapdl-command]
---

# FSSECT

PyMAPDL: `mapdl.fssect(rho='', nev='', nlod='', kbr='', **kwargs)`

Calculates and stores total linearized stress components.

## Parameters

**rho**: In-plane (X-Y) average radius of curvature of the inside and outside surfaces of an axisymmetric section. If zero (or blank), a plane or 3D structure is assumed. If nonzero, an axisymmetric structure is assumed. Use a suitably large number (see the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html)) or use -1 for an axisymmetric straight section.

**nev**: Event number to be associated with these stresses (defaults to 1).

**nlod**: Loading number to be associated with these stresses (defaults to 1).

**kbr**

For an axisymmetric analysis ( `RHO` ≠ 0):

- `0` - Include the thickness-direction bending stresses
- `1` - Ignore the thickness-direction bending stresses
- `2` - Include the thickness-direction bending stress using the same formula as the Y (axial direction ) bending stress. Also use the same formula for the shear stress.

## Notes

Calculates and stores the total linearized stress components at the ends of a section path ( [[path|PATH]] ) (as defined by the first two nodes with the [[ppath|PPATH]] command). The path must be entirely within the selected elements (that is, there must not be any element gaps along the path). Stresses are stored according to the fatigue event number and loading number specified. Locations (one for each node) are associated with those previously defined for these nodes (FL) or else they are automatically defined. Stresses are separated into six total components (SX through SXZ) and six membrane-plus-bending (SX through SXZ) components. The temperature at each end point and the current time are also stored along with the total stress components. Calculations are made from the stresses currently in the database (last [[set|SET]] or [[lcase|LCASE]] command). Stresses are stored as section coordinate components if axisymmetric or as global Cartesian coordinate components otherwise, regardless of the active results coordinate system ( [[rsys|RSYS]] ). The FSLIST command may be used to list stresses. The FS command can be used to modify stored stresses. See also the [[prsect|PRSECT]] and [[plsect|PLSECT]] commands for similar calculations.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FSSECT.html
