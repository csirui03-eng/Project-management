---
apdl: "EDWELD"
method: edweld
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edweld
generated: 2026-08-22
tags: [mapdl-command]
---

# EDWELD

PyMAPDL: `mapdl.edweld(option='', nweld='', n1='', n2='', sn='', ss='', expn='', exps='', epsf='', tfail='', nsw='', cid='', **kwargs)`

Defines a massless spotweld or generalized weld for use in an explicit

dynamic analysis.

## Parameters

**option**

Label identifying the option to be performed:

ADD - Define a weld (default). This weld may be a spotweld between two nodes or a  
generalized weld. A massless spotweld will be defined if valid node numbers are specified in fields N1 and N2. A generalized weld will be defined if a node component is specified in field N1.

DELE - Delete specified weld. If NWELD is blank, all welds are deleted.

LIST - List specified weld. If NWELD is blank, all welds are listed.

**nweld**: Reference number identifying the spotweld or generalized weld.

**n1, n2**: For a spotweld, N1 and N2 are the nodes which are connected by the spotweld. For a generalized weld, input a nodal component name in N1 and leave N2 blank. The nodal component should contain all nodes that are to be included in the generalized weld.

**sn**: Normal force at spotweld failure.

**ss**: Shear force at spotweld failure.

**expn**: Exponent for normal spotweld force.

**exps**: Exponent for shear spotweld force.

**epsf**: Effective plastic strain at ductile failure (used only for a generalized weld).

**tfail**: Failure time for constraint set (used only for a generalized weld); default = 1.0e20.

**nsw**: Number of spot welds for the generalized weld.

**cid**: Coordinate system ID number (CID) to be used for output data (used only for a generalized weld). The coordinate system must be previously defined with the EDLCS command.

## Notes

This command can be used to define a massless spotweld between two nodes or a generalized weld for a group of nodes. For a spotweld, the nodes specified by N1 and N2 must not be coincident. For a generalized weld, coincident nodes are permitted, but CID must be specified when using coincident nodes. EDWELD is not updated after a node merge operation; therefore, node merging \[NUMMRG,NODE\] should be done before any EDWELD definitions. Nodes connected by a spotweld or generalized weld cannot be constrained in any other way.

Failure of the weld occurs when:

where fn and fs are normal and shear interface forces. Normal interface force fn is nonzero for tensile values only.

You can graphically display spotwelds by issuing the command /PBC,WELD,,1.

This command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
