---
apdl: "RSYS"
method: rsys
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.controls.Controls.rsys
generated: 2026-08-22
tags: [mapdl-command]
---

# RSYS

PyMAPDL: `mapdl.rsys(kcn='', **kwargs)`

Activates a coordinate system for printout or display of element and nodal results.

## Parameters

**kcn**

The coordinate system to use for results output:

- `0` - Global Cartesian coordinate system (default, except for spectrum analyses).
- `1` - Global cylindrical coordinate system in Z.
- `2` - Global spherical coordinate system.
- `5` - Global cylindrical coordinate system in Y.
- `6` - Global cylindrical coordinate system in X.
- `> 10` - Any existing local coordinate system.
- `SOLU` - Solution coordinate systems.
- `LSYS` - Layer coordinate system (default for spectrum analysis).

## Notes

The **RSYS** command activates a coordinate system for printing or displaying element results data such as stresses and heat fluxes, and nodal results data such as degrees of freedom and reactions.

Mechanical APDL rotates the results data to the specified coordinate system during printout, display, or element table operations (such as [[prnsol|PRNSOL]], [[presol|PRESOL]], [[plnsol|PLNSOL]], and [[etable|ETABLE]] ).

You can define coordinate systems with various Mechanical APDL commands such as [[local|LOCAL]], [[cs|CS]], [[clocal|CLOCAL]], and [[cskp|CSKP]].

The **RSYS** command has no effect on beam or pipe stresses, which Mechanical APDL displays (via [[eshape|/ESHAPE]],1 and PowerGraphics) in the element coordinate system.

Element results such as stresses and heat fluxes are in the element coordinate systems when `KCN` = SOLU. Nodal requests for element results (for example, [[prnsol|PRNSOL]],S,COMP) average the element values at the common node; that is, the orientation of the node is not a factor in the output of element quantities.

For nearly all solid elements, the default element coordinate systems are parallel to the global Cartesian coordinate system.

For shell elements and the remaining solid elements, the default element coordinate system can differ from element to element.

For layered shell and layered solid elements, Mechanical APDL initially selects the element coordinate system when `KCN` = SOLU. You can then select the layer coordinate system via the [[layer|LAYER]] command.

Nodal results such as degrees of freedom and reactions can be properly rotated only if the resulting component set is consistent with the degree-of-freedom set at the node. The degree-of-freedom set at a node is determined by the elements attached to the node.

Example: If a node does not have a UZ degree of freedom during solution, any Z component resulting from a rotation does not print or display in POST1. Results at nodes with a single degree-of-freedom (UY only, for example) should therefore not be rotated; that is, they should be viewed only in the nodal coordinate system or a system parallel to the nodal system. (The default global Cartesian system cannot be parallel to the nodal system.)

Results at nodes with a 2D degree-of-freedom set (UX and UY, for example) should not be rotated out of the 2D plane.

When `KCN` \> 10, and the specified system is subsequently redefined, reissue the **RSYS** command for results to be rotated into the redefined system.

For element quantities, solution coordinate systems are the element coordinate system for each element. For nodal quantities, they are the nodal coordinate systems.

If an element or nodal coordinate system is not defined, Mechanical APDL uses the global Cartesian coordinate system.

If you issue a [[layer|LAYER]], `N` command (where `N` refers to a layer number), the results appear in the layer coordinate system. (SOLU is the default for spectrum analyses.)

The default coordinate system for certain elements, notably shells, is not global Cartesian and is frequently not aligned at adjacent elements. Avoid setting `KCN` = SOLU with such elements, as it can make nodal averaging of component element results (such as SX, SY, SZ, SXY, SYZ, and SXZ) invalid.

When post-processing expanded nodal results in a cyclic symmetry analysis ( [[cycexpand|/CYCEXPAND]] ), use of **RSYS**,SOLU is recommended so that the appropriate cyclic nodal coordinate system is used (see [[cyclic|CYCLIC]] command). For any other coordinate system (for example, **RSYS**,1), cyclic rotation is not carried out, and nodal results at all sectors are expressed in the specified coordinate system ( `KCN` ). See [Result Coordinate System](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycpost.html#advcycrescosys)

For layered shell and solid elements, the results appear in their respective layer coordinate systems. For a specific layer of interest, issue a [[layer|LAYER]], `N` command (where `N` refers to a layer number).

If a model has both nonlayered and layered elements, you can use **RSYS**,SOLU and **RSYS** ,LSYS simultaneously (with **RSYS**,SOLU applicable to nonlayered elements and **RSYS**,LSYS applicable to layered elements).

To reverse effects of the LSYS option, issue an **RSYS**,0 command.

LSYS is the default for spectrum analysis.

Mechanical APDL plots [[plvect|PLVECT]] vector arrow displays (such temperature, velocity, and force) in the global Cartesian coordinate system ( **RSYS** = 0). Subsequent operations revert to your original coordinate system.

When using solution coordinate systems for results output ( **RSYS**,SOLU), the deformed or displaced shape in a POST1 contour display can be unexpected (although the contours are displayed in the expected colors). The program does not rotate displacement values (Ux,Uy,Uz) to global; instead, the displacements (stored locally) are added directly to the global coordinates (X,Y,Z). For example, if in PREP7 the nodes are rotated 90 degrees about the z axis and the global Uy displacements are relatively large, the Ux values will be large, causing the model to display a large deformation in the global X direction.

If large deflection is active ( [[nlgeom|NLGEOM]],ON), Mechanical APDL rotates the element component result directions by the amount of rigid body rotation.

Mechanical APDL displays the element component results in the initial global coordinate system for the following elements: `SHELL181`, `SHELL281`, `ELBOW290`, `PLANE182`, `PLANE183`, `SOLID185`, `SOLID186`, `SOLID187`, `SOLID272`, `SOLID273`, `SOLID285`, `SOLSH190`, `SHELL208`, and `SHELL209`.

All other element result transformations, therefore, are also relative to the initial global system.

Nodal degree-of-freedom results are based on the initial geometry.

For all other element types, component results displayed in the co-rotated coordinate system include the element rigid body rotation from the initial global coordinate system, and all other element result transformations are relative to the rotated global system.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RSYS.html
