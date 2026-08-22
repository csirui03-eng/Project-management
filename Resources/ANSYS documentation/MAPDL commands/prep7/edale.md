---
apdl: "EDALE"
method: edale
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edale
generated: 2026-08-22
tags: [mapdl-command]
---

# EDALE

PyMAPDL: `mapdl.edale(option='', afac='', bfac='', dfac='', efac='', start='', end='', **kwargs)`

Assigns mesh smoothing to explicit dynamic elements that use

the ALE formulation.

## Parameters

**option**

Label identifying the option to be performed:

ADD - Add smoothing controls (default).

DELETE - Delete smoothing controls.

LIST - List smoothing controls.

**afac**: Simple average smoothing weight factor (default = 0).

**bfac**: Volume weighted smoothing weight factor (default = 0).

**dfac**: Equipotential smoothing weight factor (default = 0).

**efac**: Equilibrium smoothing weight factor (default = 0). EFAC is only applicable to PLANE162 elements.

**start**: Start time for ALE smoothing (default = 0).

**end**: End time for ALE smoothing (default = 1e20).

## Notes

Mesh smoothing specified by the EDALE command is only applicable to PLANE162 and SOLID164 elements that are flagged to use the ALE formulation (KEYOPT(5) = 1). To activate the ALE formulation, you must specify at least one smoothing weight factor on this command and the number of cycles between advection (NADV) on the EDGCALE command. See Arbitrary Lagrangian-Eulerian Formulation in the ANSYS LS-DYNA User's Guide for more information.

The EDALE command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
