---
apdl: "EDLCS"
method: edlcs
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edlcs
generated: 2026-08-22
tags: [mapdl-command]
---

# EDLCS

PyMAPDL: `mapdl.edlcs(option='', cid='', x1='', y1='', z1='', x2='', y2='', z2='', x3='', y3='', z3='', **kwargs)`

Defines a local coordinate system for use in explicit dynamics

analysis.

## Parameters

**option**

Label identifying the option to be performed:

ADD - Define a coordinate system (default).

DELE - Delete a coordinate system. If CID is blank, all coordinate systems are  
deleted.

LIST - List defined coordinate systems. If CID is blank, all coordinate systems are  
listed.

**cid**: Coordinate system ID.

**x1, y1, z1**: X, Y, and Z coordinates of a point on the local x-axis.

**x2, y2, z2**: X, Y, and Z coordinates of a point on the local x-y plane.

**x3, y3, z3**: X, Y, and Z coordinates of the origin. X3, Y3, and Z3 all default to zero.

## Notes

Local coordinate systems defined by this command are used in an explicit dynamic analysis. For example, a local coordinate system may be used when defining orthotropic material properties (see EDMP).

The coordinate system is defined by 2 vectors, one from the origin (X3, Y3, Z3) to a point on the x-axis (X1, Y1, Z1), and one from the origin to a point on the x-y plane (X2, Y2, Z2). The cross product of these two vectors determines the z-axis, and the cross product of the z-axis vector and x-axis vector determines the y-axis. If X3, Y3, and Z3 are not specified, the global origin (0,0,0) is used by default (as shown in the figure below).

The x-axis vector and the xy vector should be separated by a reasonable angle to avoid numerical inaccuracies.

When you use the local coordinate system (defined by the EDLCS command) to define a load (EDLOAD command), the direction of the load will depend on the load type. For force and moment loads (Lab = FX, MX, etc. on EDLOAD), the load will be applied in the direction of the local coordinate system defined by EDLCS. For prescribed motion degrees of freedom (Lab = UX, ROTX, VX, AX, etc. on EDLOAD), the motion will act in the direction of a vector from point (X1, Y1, Z1) to point (X2, Y2, Z2) as input on EDLCS. See the EDLOAD command for more information.

This command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
