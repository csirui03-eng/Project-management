---
apdl: "EDIPART"
method: edipart
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edipart
generated: 2026-08-22
tags: [mapdl-command]
---

# EDIPART

PyMAPDL: `mapdl.edipart(part='', option='', cvect='', tm='', ircs='', ivect='', vvect='', cid='', **kwargs)`

Defines inertia for rigid parts in an explicit dynamics analysis.

## Parameters

**part**: Part number for which the inertia is defined (the part number must have been previously generated using the EDPART command). The part should be composed of a rigid material (EDMP,RIGID). For Option = ADD, you must input a value; there is no default. For Option = DELE or LIST, PART defaults to all parts.

**option**

ADD - Define inertia for the specified PART (default).

DELE - Delete the inertia properties for the specified PART. The remaining fields are  
ignored. If PART is blank, inertia properties previously specified using EDIPART are deleted for all rigid parts.

LIST - List the inertia properties for the specified PART. The remaining fields are  
ignored. If PART is blank, inertia properties are listed for all rigid parts.

**cvect**: The vector containing the global Cartesian coordinates of the center of mass for the part. This vector must have been previously defined with a dimension of three (`*DIM` command) and filled in as shown below. If Cvect is blank, the global Cartesian origin (0,0,0) is used as the center of mass.

**tm**: Translation mass (no default, must be defined).

**ircs**

Flag for inertia tensor reference coordinate system.

0 (or blank) - Global inertia tensor (default). You must supply all six inertia tensor  
components (see Ivect).

1 - Principal moments of inertia with orientation vectors. You must supply IXX,  
IYY, IZZ (see Ivect) and CID.

**ivect**: The name of a vector containing the components of the inertia tensor. This vector must have been previously defined (`*DIM` command) with a dimension of six and filled in as shown below. Vector entries 2, 3, and 5 are ignored if IRCS = 1. There is no default for this vector; it must be specified.

**vvect**: The name of a vector containing the initial velocity (relative to the global Cartesian coordinate system) of the rigid part. This vector must have been previously defined (`*DIM` command) with a dimension of six and filled in as shown below. If Vvect is blank, the initial velocity defaults to zero.

**cid**: Local coordinate system ID. This coordinate system must have been previously defined with the EDLCS command. You must input CID if IRCS = 1 (no default).

## Notes

The EDIPART command applies only to rigid parts (EDMP,RIGID). It allows you to input the inertia properties for the rigid part rather than having the program calculate the properties from the finite element mesh.

This command is also valid in Solution.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
