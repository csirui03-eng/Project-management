---
apdl: "EDADAPT"
method: edadapt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edadapt
generated: 2026-08-22
tags: [mapdl-command]
---

# EDADAPT

PyMAPDL: `mapdl.edadapt(part='', key='', **kwargs)`

Activates adaptive meshing in an explicit dynamic analysis.

## Parameters

**part**: Part ID (number) for which adaptive meshing is to be turned on (or off). Use PART = STAT to list the current adaptive meshing definitions.

**key**

Adaptivity key:

OFF - Do not use adaptive meshing for the specified part ID (default).

ON - Use adaptive meshing for the specified part ID.

## Notes

When adaptive meshing (adaptivity) is turned on, the mesh will automatically be regenerated to ensure adequate element aspect ratios. Adaptive meshing is most commonly used in the analysis of large deformation processes such as metal forming, in which the blank would need to be adaptively meshed.

Adaptive meshing is only valid for parts consisting of SHELL163 elements. By default, adaptive meshing is OFF for all parts in the model. To specify adaptive meshing for more than one part in the model, you must issue the EDADAPT command for each part ID. Use the EDPART command to create and list valid part IDs. Use the EDCADAPT command to define additional adaptive meshing parameters.

The EDADAPT command is not supported in an explicit dynamic full restart analysis (EDSTART,3). In addition, a full restart cannot be performed successfully if adaptive meshing was used in the previous analysis.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
