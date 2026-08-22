---
apdl: "EDNB"
method: ednb
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.ednb
generated: 2026-08-22
tags: [mapdl-command]
---

# EDNB

PyMAPDL: `mapdl.ednb(option='', cname='', ad='', as_='', **kwargs)`

Defines a nonreflecting boundary in an explicit dynamic analysis.

## Parameters

**option**

Label identifying the nonreflecting boundary option to be performed.

ADD - Define a nonreflecting boundary (default).

DELE - Delete a nonreflecting boundary.

LIST - List all defined nonreflecting boundaries (remaining fields are ignored).

**cname**: Name of existing nodal component to which the nonreflecting boundary is to be added or deleted. For Option = DELE, use Cname = ALL to delete all defined nonreflecting boundaries.

**ad**

Activation flag for dilatational waves (dampers normal to waves).

0 - Dilatational activation flag is off (default).

1 - Dilatational activation flag is on.

**as_**

Activation flag for shear waves (dampers tangent to waves).

0 - Shear activation flag is off (default).

1 - Shear activation flag is on.

## Notes

Nonreflecting boundaries can be defined on the external surfaces of SOLID164 and SOLID168 elements that are being used to model an infinite domain. They are typically used in geomechanical applications to limit the size of the model. For example, when a half space is being modeled with a finite geometry, the nonreflecting boundary option can be used to prevent artificial stress wave reflections generated at the boundary from reentering the model and contaminating the results.

When using nonreflecting boundaries, you should not constrain the nodes at the boundary; doing so would negate the presence of the dampers. Usually, the large mass of the finite domain is sufficient to resist motion.

This command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
