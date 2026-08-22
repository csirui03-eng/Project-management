---
apdl: "EDRI"
method: edri
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edri
generated: 2026-08-22
tags: [mapdl-command]
---

# EDRI

PyMAPDL: `mapdl.edri(option='', part='', xc='', yc='', zc='', tm='', ixx='', iyy='', izz='', ixy='', iyz='', ixz='', **kwargs)`

Defines inertia properties for a new rigid body that is created when a

deformable part is switched to rigid in an explicit dynamic analysis.

## Parameters

**option**

Label identifying the option to be performed.

ADD - Define inertia for specified part (default).

DELE - Delete inertia definition for specified part.

LIST - List inertia definitions.

**part**: Part number for which inertia is defined (no default).

**xc, yc, zc**: X, Y, and Z-coordinates of the center of mass (no defaults).

**tm**: Translational mass (no default).

**ixx, iyy, izz, ixy, iyz, ixz**: Components (xx, yy, etc.) of inertia tensor. IXX, IYY, and IZZ must be input (no defaults). IXY, IYZ, and IXZ default to zero.

## Notes

Use this command to define inertia properties for a rigid body that is created when a deformable part is switched to rigid (using the EDRD,D2R command) in an explicit dynamic analysis. If these properties are not defined, LS-DYNA will compute the new rigid body properties from the finite element mesh (which requires an accurate mesh representation of the body). When rigid bodies are merged to a master rigid body, the inertia properties defined for the master rigid body apply to all members of the merged set.

EDRI can only be issued in a new analysis. Therefore, if you are going to use inertia properties in a subsequent restart analysis, you must issue EDRI in the original analysis for the part that will later be switched to rigid in the restart.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
