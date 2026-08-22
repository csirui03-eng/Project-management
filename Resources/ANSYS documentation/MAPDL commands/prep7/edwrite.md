---
apdl: "EDWRITE"
method: edwrite
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# EDWRITE

PyMAPDL: `mapdl.edwrite(option='', fname='', ext='', **kwargs)`

Writes explicit dynamics input to an LS-DYNA input file.

## Parameters

**option**

Sets a flag in the LS-DYNA input file (Fname.Ext) to produce desired output.

ANSYS - Set a flag to write results files for the ANSYS  
postprocessors (default). The files that will be written are Jobname.RST and Jobname.HIS (see Notes below).

LSDYNA - Set a flag to write results files for the LS-DYNA  
postprocessor (LS-POST). The files that will be written are D3PLOT, and files specified by EDOUT and EDHIST (see Notes below).

BOTH - Set a flag to write results files for both ANSYS and LS-DYNA postprocessors.

**fname**: File name and directory path (80 characters maximum, including directory; this limit is due to an LS-DYNA program limitation). If you do not specify a directory path, it will default to your working directory. The file name defaults to Jobname. Previous data on this file, if any, are overwritten.

**ext**: Filename extension (eight-character maximum).

## Notes

This command writes an LS-DYNA input file for the LS-DYNA solver. EDWRITE is only valid if explicit dynamic elements have been specified. This command is not necessary if the LS-DYNA solver is invoked from within ANSYS, in which case Jobname.K (or Jobname.R) is written automatically when the solution is initiated. (If LS-DYNA is invoked from within ANSYS, use EDOPT to specify desired output.)

If the analysis is a small restart (EDSTART,2), the file that is written will have the name Jobname.R (by default) and will only contain changes from the original analysis.

If the analysis is a full restart (EDSTART,3), the file that is written will have the name Jobname_nn.K (by default) and will contain all the information from the database. In a full restart, the jobname is changed to Jobname_nn (nn = 01 initially, and is incremented for each subsequent full restart.)

A command is included in the LS-DYNA input file to instruct the LS-DYNA solver to write the results files indicated by Option. By default, LS- DYNA will write the ANSYS results file Jobname.RST (see the EDRST command). If Jobname.HIS is desired, you must also issue EDHIST.

Option = LSDYNA or BOTH will cause LS-DYNA to write results files for the LS-POST postprocessor. The D3PLOT file is always written for these two options. If other LS-POST files are desired, you must issue the appropriate EDHIST and EDOUT commands.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
