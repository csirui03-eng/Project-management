---
apdl: "EDGCALE"
method: edgcale
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edgcale
generated: 2026-08-22
tags: [mapdl-command]
---

# EDGCALE

PyMAPDL: `mapdl.edgcale(nadv='', meth='', **kwargs)`

Defines global ALE controls for an explicit dynamic analysis.

## Parameters

**nadv**: Number of cycles between advection (default = 0).

**meth**

Advection method.

0 - Donor cell + Half Index Shift (first order accurate) (default).

1 - Van Leer + Half Index Shift (second order accurate).

## Notes

This command sets global ALE controls in an explicit dynamic analysis. These ALE controls apply to all PLANE162 or SOLID164 elements in the model that are flagged to use the ALE formulation (KEYOPT(5) = 1). To activate the ALE formulation, you must specify the number of cycles between advection on this command and at least one smoothing weight factor on the EDALE command. See Arbitrary Lagrangian-Eulerian Formulation in the ANSYS LS-DYNA User's Guide for more information.

To see the current EDGCALE settings, issue the command EDALE,LIST.

The EDGCALE command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
