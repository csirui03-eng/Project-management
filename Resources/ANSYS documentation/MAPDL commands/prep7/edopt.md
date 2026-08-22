---
apdl: "EDOPT"
method: edopt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edopt
generated: 2026-08-22
tags: [mapdl-command]
---

# EDOPT

PyMAPDL: `mapdl.edopt(option='', value='', **kwargs)`

Specifies the type of output for an explicit dynamics analysis.

## Parameters

**option**

Label identifying the option to be performed:

ADD - Define an output type specification (default).

DELE - Delete an output type specification.

LIST - List the current output type specification.

**value**

Label identifying the type of output that the LS-DYNA solver should produce:

ANSYS - Write results files for the ANSYS postprocessors  
(default). The files that will be written are Jobname.RST and Jobname.HIS (see "Notes" below).

LSDYNA - Write results files for the LS-DYNA postprocessor  
(LS-POST). The files that will be written are D3PLOT, and files specified by EDOUT and EDHIST (see "Notes" below).

BOTH - Write results files for both ANSYS and LS-DYNA postprocessors.

## Notes

By default, LS-DYNA will write the ANSYS results file Jobname.RST (see the EDRST command.) If Jobname.HIS is desired, you must also issue EDHIST.

Value = LSDYNA or BOTH will cause LS-DYNA to write results files for the LS-POST postprocessor. The D3PLOT file is always written for these two options. If other LS-POST files are desired, you must issue the appropriate EDHIST and EDOUT commands.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
