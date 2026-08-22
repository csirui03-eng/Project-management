---
apdl: "PRSECT"
method: prsect
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.prsect
generated: 2026-08-22
tags: [mapdl-command]
---

# PRSECT

PyMAPDL: `mapdl.prsect(rho='', kbr='', kbr3d='', **kwargs)`

Calculates and prints linearized stresses along a section path.

## Parameters

**rho**: In-plane (X-Y) average radius of curvature of the inside and outside surfaces of an axisymmetric section. If zero (or blank), a plane or 3D structure is assumed. If nonzero, an axisymmetric structure is assumed. Use any large number (or -1) for an axisymmetric straight section.

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

You may want to linearize the stresses through a section and separate them into categories for various code calculations. **PRSECT** calculates and reports linearized stresses along a section path. The linearized stresses are also separated into membrane, bending, membrane plus bending, peak, and total stress categories.

Define your section path ( [[path|PATH]] and [[ppath|PPATH]] with the NODE option). Your path must lie entirely within the selected set of elements (that is, no element gaps may exist along the path). [[path|PATH]] and [[ppath|PPATH]] only retrieve the two end nodes; the path data is not retained. The section path is defined by the two end nodes, and by 47 intermediate points that are automatically determined by linear interpolation in the active display coordinate system ( [[dsys|DSYS]] ). The number and location of the intermediate points are not affected by the number of divisions set by [[path|PATH]],, `nDiv`.

Your linearized component stress values are obtained by interpolating each element's average corner nodal values along the section path points within each path element. **PRSECT** reports the linearized component and principal stresses for each stress category at the beginning, mid-length, and end of the section path. [[prpath|PRPATH]] can be used to report the total stresses at the intermediate points.

Section paths can be through any set of solid (2D plane, 2D axisymmetric or 3D) elements; however, section paths are usually defined to be through the thickness of the structure and normal to the inner and outer structure surfaces. Section paths (in-plane only) can also be defined for shell element structures.

If the `RHO` option is set to indicate the axisymmetric option (non-zero), **PRSECT** reports the linearized stresses in the section coordinates (SX - along the path, SY - normal to the path, and SZ - hoop direction). If the `RHO` option is set to indicate the 2D planar or 3D option (zero or blank), **PRSECT** reports the linearized stresses in the active results coordinate system ( [[rsys|RSYS]] \]. If the `RHO` option is zero or blank and either [[rsys|RSYS]], SOLU or [[rsys|RSYS]], -1 are active, the linearized stresses are calculated and reported in the global Cartesian coordinate system.

Linearized stress calculations should be performed in a rectangular coordinate system. Principal stresses are recalculated from the component stresses and are invariant with the coordinate system as long as SX is in the same direction at all points along the defined path. The [[plsect|PLSECT]] command displays the linearized stresses in the same coordinate system as reported by **PRSECT**.

Stress components through the section are linearized by a line integral method and separated into constant membrane stresses, bending stresses varying linearly between end points, and peak stresses (defined as the difference between the actual (total) stress and the membrane plus bending combination).

For nonaxisymmetric structures, the bending stresses are calculated such that the neutral axis is at the midpoint of the path. Axisymmetric results include the effects of both the radius of revolution (automatically determined from the node locations) and the in-plane average radius of curvature of the section surfaces (user input).

For axisymmetric cases, Mechanical APDL calculates the linearized bending stress in the through- thickness direction as the difference between the total outer fiber stress and the membrane stress if `KBR` = 0. The calculation method may be conservative for locations with a highly nonlinear variation of stress in the through-thickness direction. Alternatively, you can specify `KBR` = 2 to calculate the bending stress using the same method and formula as the Y (axial direction) bending stress. For more information, see the discussion of [axisymmetric cases](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_post4.html#eqa0e44427-d764-4797-9c99-13f056f2227c) (specifically ) in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html).

In analyses of 3D models with `RHO` = 0, ignoring the calculated out-of-plane bending stresses is recommended in some scenarios when determining the linearized bending stresses. If `KBR3D` = 0, all calculated stresses are included in the linearized bending-stress calculations. If `KBR3D` = 1, these calculated out-of-plane bending stresses are ignored in the linearized bending-stress calculations: SX, SXY, SXZ. (The principal bending-stress calculation for S1, S2, S3, SINT, and SEQV is performed with these zeroed components.)

Portions of this command are not supported by PowerGraphics ( [[graphics|/GRAPHICS]],POWER\].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRSECT.html
