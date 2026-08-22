---
apdl: "EDBOUND"
method: edbound
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edbound
generated: 2026-08-22
tags: [mapdl-command]
---

# EDBOUND

PyMAPDL: `mapdl.edbound(option='', lab='', cname='', xc='', yc='', zc='', cname2='', copt='', **kwargs)`

Defines a boundary plane for sliding or cyclic symmetry.

## Parameters

**option**

Label identifying the symmetry plane option to be performed.

ADD - Define a sliding or cyclic symmetry plane.

DELE - Delete a specified sliding or cyclic symmetry plane.

LIST - List defined sliding or cyclic symmetry planes.

**lab**

Valid boundary options for defining a symmetry plane. A valid label must always be specified for adding, deleting, or listing boundary planes.

SLIDE - Sliding symmetry plane.

CYCL - Cyclic symmetry plane.

**cname**: Name of existing component \[CM\] to which boundary symmetry is to be applied or deleted. Component must consist of nodes. For Option = LIST, a component is not required because all defined symmetry planes are listed for the specified Lab. For Option = DELE, use Cname = ALL to delete all symmetry planes currently defined for the specified Lab.

**xc, yc, zc**: X, Y, and Z coordinates of the head of the vector defining normal (Lab = SLIDE) or axis of rotation (Lab = CYCL). The tail of the vector is at the global origin.

**cname2**: Name of existing nodal component \[CM\] for which second cyclic boundary plane is to be applied. Each node in Cname2 component is constrained to a corresponding node in the first component set. Therefore, component Cname2 must have the same number of nodes as the Cname component. Cname2 is valid only for Lab = CYCL.

**copt**

Specified constraint option for sliding plane symmetry. COPT is valid only for Lab = SLIDE. Valid COPT options are:

0 - Nodes move on normal plane (default).

1 - Nodes move only in vector direction.

## Notes

For cyclic symmetry, the node numbers in component Cname2 must differ from the node numbers in Cname by a constant offset value. In addition, the nodes in Cname2 must have locations which, if given in cylindrical coordinates, all differ by the same angle from the nodes in Cname. The following figure shows how you would define components for a cyclic symmetry plane.

This command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
