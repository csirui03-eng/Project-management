---
apdl: "EDCMORE"
method: edcmore
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edcmore
generated: 2026-08-22
tags: [mapdl-command]
---

# EDCMORE

PyMAPDL: `mapdl.edcmore(option='', num='', val1='', val2='', **kwargs)`

Specifies additional contact parameters for a given contact definition

in an explicit dynamic analysis.

## Parameters

**option**

Label identifying the option to be performed.

ADD - Define contact parameters for the contact entity specified by NUM (default).

DELE - Delete contact parameters (VAL1 and VAL2) for the  
contact entity specified by NUM. If NUM = ALL, all contact parameters previously defined by EDCMORE are deleted.

**num**: Contact entity number. This contact entity must have been previously defined with the EDCGEN command. Use EDCLIST to obtain a list of contact entity numbers.

**val1**: Penalty scale factor for slave (contact) surface (SFS); default = 1.

**val2**: Penalty scale factor for master (target) surface (SFM); default = 1.

## Notes

You can use the EDCMORE command to specify two additional contact parameters (SFS and SFM) for a specific contact definition. These parameters will apply only to the contact entity number entered on the NUM field. Use the EDCLIST command to obtain a list of contact definitions and their corresponding contact entity numbers. The listing produced by EDCLIST will include any contact parameters specified with the EDCMORE command.

When you use the EDDC command to delete a contact definition, any parameters you specified with EDCMORE for that contact definition will also be deleted. To delete only the parameters specified by EDCMORE for a given contact definition, use the command EDCMORE,DELE,NUM.

Note: When you delete a contact definition with the EDDC command, the contact entity numbers will be renumbered for the remaining contact definitions. Therefore, you should always issue EDCLIST to obtain a current list of contact entity numbers before adding or deleting contact parameters with the EDCMORE command.

The EDCMORE command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
