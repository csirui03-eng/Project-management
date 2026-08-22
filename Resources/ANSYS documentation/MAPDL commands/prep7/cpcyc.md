---
apdl: "CPCYC"
method: cpcyc
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.cpcyc
generated: 2026-08-22
tags: [mapdl-command]
---

# CPCYC

PyMAPDL: `mapdl.cpcyc(lab='', toler='', kcn='', dx='', dy='', dz='', knonrot='', kmid='', ceopt='', **kwargs)`

Couples the two side faces of a cyclically symmetric model for loadings that are the same on every segment.

## Parameters

**lab**: Degree of freedom label for coupled nodes (in the nodal coordinate system). If ALL, use all appropriate labels. Valid labels are: Structural labels: UX, UY, or UZ (displacements); ROTX, ROTY, or ROTZ (rotations, in radians). Thermal label: TEMP (temperature). Fluid label: PRES (pressure). Electric label: VOLT (voltage).

**toler**: Tolerance for coincidence (based on maximum coordinate difference in each global Cartesian direction for node locations and on angle differences for node orientations). Defaults to 0.0001. Only nodes within the tolerance are considered to be coincident for coupling.

**kcn**: In coordinate system `KCN`, two nodes are coupled when the coordinates of the first node (on the low boundary) plus the increments DX, DY, and DZ match the coordinates of the second node (on the high boundary).

**dx**, **dy**, **dz**: Node location increments in the active coordinate system (DR, Dθ, DZ for cylindrical, DR, D θ, DΦ for spherical or toroidal).

**knonrot**: When `KNONROT` = 0, the nodes on coupled sets are rotated into coordinate system `KCN` (see [[nrotat|NROTAT]] command description). When `KNONROT` = 1, the nodes are not rotated, and you should make sure that coupled nodal DOF directions are correct.

**kmid**: When `KMID` = 1, the midside nodes of the element edges are added to the coupled sets of the end nodes of edges with specified nodal DOFs, if the end nodes of an edge are coupled. By default ( `KMID` = 0), the midside nodes are not included in the coupled sets.

**ceopt**: When `CEOPT` = 1, the coupled sets are converted to constraint equations. Use this option to improve performance in a distributed-memory parallel ( DMP ) solution. By default ( `CEOPT` = 0), the coupled sets are not converted to constraint equations.

## Notes

Cyclic coupling requires identical node and element patterns on the low and high sector boundaries. The [[mshcopy|MSHCOPY]] operation allows convenient generation of identical node and element patterns. See [Using CPCYC and MSHCOPY Commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_8.html#) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for more information.

Although developed initially for use with cyclically symmetric models, use of the **CPCYC** command is not limited to cyclic symmetry analyses.

**Example Usage** [Using CPCYC and MSHCOPY Commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_8.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CPCYC.html
