---
apdl: "EDCLIST"
method: edclist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edclist
generated: 2026-08-22
tags: [mapdl-command]
---

# EDCLIST

PyMAPDL: `mapdl.edclist(num='', **kwargs)`

Lists contact entity specifications in an explicit dynamics analysis.

## Parameters

**num**: Number identifying contact entity to be listed. Use NUM = ALL to list all contact entities (ALL is the default).

## Notes

Lists contact entity specifications previously defined with the EDCGEN command. The listing will include any contact parameters defined using the EDCMORE command.

This command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
