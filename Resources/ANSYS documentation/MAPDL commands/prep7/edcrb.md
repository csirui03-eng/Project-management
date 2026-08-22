---
apdl: "EDCRB"
method: edcrb
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edcrb
generated: 2026-08-22
tags: [mapdl-command]
---

# EDCRB

PyMAPDL: `mapdl.edcrb(option='', neqn='', partm='', parts='', **kwargs)`

Constrains two rigid bodies to act as one in an explicit dynamics

analysis.

## Parameters

**option**

Label identifying the option to be performed:

ADD - Define an equation to constrain two rigid bodies (default).

DELE - Delete the equation (specified by NEQN) that constrains two rigid bodies. If  
NEQN is blank, all equations constraining rigid bodies are deleted.

LIST - List constrained rigid bodies specified by NEQN. If NEQN is blank, all  
constrained rigid bodies are listed.

**neqn**: Equation reference number. Defaults to PARTS. NEQN should be a unique number for each pair of PARTM and PARTS. If it is not unique, the equation reference number defined last will overwrite any previously defined NEQN with the same number.

**partm**: PART number \[EDPART\] identifying the master rigid body. This value is ignored if the DELE or LIST labels are specified. No default; you must enter a value.

**parts**: PART number \[EDPART\] identifying the slave rigid body. This value is ignored if the DELE or LIST labels are specified. No default; you must enter a value.

## Notes

EDCRB is valid only for materials defined as rigid bodies with the EDMP,RIGID command. EDCRB automatically generates a constraint equation to force the specified rigid bodies to behave as a single rigid body. The slave rigid body takes on the material properties and loading of the master rigid body. Any loads \[EDLOAD\] existing on the slave rigid body are ignored.

To create a single large rigid body from several smaller bodies, use a series of EDCRB commands. With the first command, specify a master and slave to create the first combined rigid body. Then, using that body as the master, specify another slave to create a larger rigid body. Continue the process, using the expanding rigid body as the master and adding slave bodies until you have defined the desired large rigid body. All slave rigid bodies will take on the material properties and loading of the original master rigid body. Note that you will need to use different NEQN values for each pair of PARTM and PARTS. This command will be ignored if you specify the previously-defined master rigid body as a slave rigid body in the same analysis. To change the master and slave definitions, first use the DELE option to delete all master and slave definitions, and then use the ADD option to redefine them.

The equation number, NEQN, is a reference number by which the constrained bodies can be identified for listing and deleting purposes on the EDCRB command. For any other reference to the constrained bodies (loading, contact definitions, etc.), use the master body part number (PARTM).

This command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
