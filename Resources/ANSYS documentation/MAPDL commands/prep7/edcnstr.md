---
apdl: "EDCNSTR"
method: edcnstr
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edcnstr
generated: 2026-08-22
tags: [mapdl-command]
---

# EDCNSTR

PyMAPDL: `mapdl.edcnstr(option='', ctype='', comp1='', comp2='', val1='', **kwargs)`

Defines various types of constraints for an explicit dynamic analysis.

## Parameters

**option**

Label identifying the option to be performed.

ADD - Define a constraint (default).

DELE - Delete the constraint specified by Ctype, Comp1, and Comp2. If Ctype = ALL, all  
constraints are deleted.

LIST - List all of the constraints previously defined by the EDCNSTR command.

**ctype**

Constraint type. The command format will vary, depending on the Ctype value.

ENS - Extra node set added to an existing rigid body.

NRB - Nodal rigid body.

STS - Tie between a shell edge and solid elements.

RIVET - Massless rivet between two noncoincident nodes.

## Notes

The EDCNSTR command allows you to define several types of constraints in an explicit dynamic analysis. A brief description of each constraint type is given below. See Constraints and Initial Conditions in the ANSYS LS-DYNA User's Guide for more information.

Extra Node Set Added to a Rigid Body (Ctype = ENS)

The ability to add extra nodes to an existing rigid body has many potential applications, including placing nodes where joints will be attached between rigid bodies, defining nodes where point loads will be applied, and defining a lumped mass at a specific location. The extra nodes specified by Comp2 may be located anywhere in the model and may have coordinates outside those of the original rigid body specified by Comp1.

Nodal Rigid Body (Ctype = NRB)

Unlike typical rigid bodies that are defined with the EDMP command, nodal rigid bodies defined with the EDCNSTR command are not associated with a part number. This can be advantageous for modeling rigid (welded) joints in a model. For a rigid joint, portions of different flexible components (having different MAT IDs) act together as a rigid body. It is difficult to define this type of rigid body with a unique MAT ID (and corresponding part number). However, the rigid joint can be easily defined using a nodal rigid body.

Shell Edge to Solid Tie (Ctype = STS)

The STS option ties regions of solid elements to regions of shell elements. A single shell node may be tied to up to nine brick element nodes that define a "fiber" vector. Solid element nodes constrained in this way remain linear throughout the analysis but can move relative to each other in the fiber direction.

Rivet between Two Nodes (Ctype = RIVET)

The RIVET option defines a massless rigid constraint between two nodes, similar to spotwelds defined with the EDWELD command. Unlike a spotweld, however, rivets contain nodes that are noncoincident, and failure cannot be specified. When a rivet is defined, the distance between the nodes is kept constant throughout any motion that occurs during a simulation. Nodes connected by a rivet cannot be part of any other constraints specified in the model.

The EDCNSTR command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
