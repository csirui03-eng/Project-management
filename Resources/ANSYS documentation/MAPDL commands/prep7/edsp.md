---
apdl: "EDSP"
method: edsp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edsp
generated: 2026-08-22
tags: [mapdl-command]
---

# EDSP

PyMAPDL: `mapdl.edsp(option='', min_='', max_='', inc='', **kwargs)`

Specifies small penetration checking for contact entities in an

explicit dynamic analysis.

## Parameters

**option**

Label identifying the option to be performed (no default).

ON - Turn small penetration checking on for specified contact entities.

OFF - Turn small penetration checking off for specified contact entities.

LIST - List current setting for penetration checking.

**min_**: Minimum contact entity number for which to turn on/off small penetration check (default = 1).

**max_**: Maximum contact entity number for which to turn on/off small penetration check (defaults to MIN).

**inc**: Contact entity number increment (default = 1).

## Notes

This command controls small penetration checking in an explicit dynamic analysis. EDSP is applicable only to the following contact types: STS, NTS, OSTS, TNTS, and TSTS. The penetration checking specified by EDSP is similar to PENCHK on the EDCONTACT command. However, EDSP controls penetration checking for individual contact entities whereas PENCHK is a global control that applies to all defined contact (of the types mentioned above). EDSP can be used in a new analysis, or in a small restart (EDSTART,2).

Use the EDCLIST command to list the contact entity numbers for all defined contact.

This command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
