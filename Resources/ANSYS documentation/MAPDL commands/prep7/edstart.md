---
apdl: "EDSTART"
method: edstart
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edstart
generated: 2026-08-22
tags: [mapdl-command]
---

# EDSTART

PyMAPDL: `mapdl.edstart(restart='', memory='', fsize='', dumpfile='', **kwargs)`

Specifies status (new or restart) of an explicit dynamics analysis.

## Parameters

**restart**

Status of the analysis (new or restart).

0 - New analysis (default).

1 - Simple restart.

2 - Small restart.

3 - Full restart.

**memory**: Memory to be used (in words). If blank, LS-DYNA assigns a value (default). If more or less memory is needed, specify the number of words (a word is usually 32 bits on a workstation).

**fsize**: Scale factor for binary file sizes. Defaults to 7, which is (7x262144) = 1835008 words.

**dumpfile**: Name of dump file to use during a restart (for example, d3dumpnn, where nn = 01, 02, 03,...,99 and defaults to 01). Leave this field blank when running a new analysis (RESTART = 0) so that the default dump file d3dump01 will be created.

## Notes

EDSTART can be issued before the SOLVE command to specify a new analysis, a simple restart, a small restart, or a full restart as described below.

New analysis: For a new analysis, you do not need to issue EDSTART unless you want to change the MEMORY or FSIZE option. If you do not specify the dump file name, d3dump01 will be created by default.

Simple restart: This option assumes that the database has not been altered. Upon restarting, results will be appended to the existing results files. Issue EDSTART,1,,,d3dumpnn to indicate which restart file to use as a starting point. The dump file to be used must have been created in an earlier run and must be available at the time this command is issued. You would typically use a simple restart when you interrupt the LS-DYNA run via Ctrl+C and terminate the run prematurely by issuing the "sense switch control" key SW1 (see Solution Control and Monitoring in the ANSYS LS-DYNA User's Guide). At this point you should be able to view the partial solution using ANSYS postprocessors. After you are done viewing the partial solution, you can reenter the solution processor and issue EDSTART,1,,,d3dumpnn, followed by SOLVE to continue with the analysis. The results will be appended to the results files Jobname.RST and Jobname.HIS. You can perform multiple simple restarts by issuing EDSTART,1,,,d3dumpnn multiple times, as needed. The solutions in the Jobname.RST file will all be in load step number 1.

Small restart: This option can be used when minor changes in the database are necessary. For example, you can reset the termination time, reset the output interval, add displacement constraints, change initial velocities, switch parts from a deformable to rigid state, etc. (See A Small Restart in theANSYS LS-DYNA User's Guide for a complete description of database items that can be changed.) Issue EDSTART,2,,,d3dumpnn followed by the commands required to change the database, then issue SOLVE. The results will be appended to the results files Jobname.RST and Jobname.HIS. You can perform multiple restarts by issuing EDSTART,2,,,d3dumpnn multiple times, as needed. The additional restart solutions will be stored in Jobname.RST as load step numbers 2, 3, etc.

Full restart: A full restart is appropriate when many modifications to the database are required. For example, you can change the model geometry, apply different loading conditions, etc. Issue EDSTART,3,,,d3dumpnn to denote a full restart analysis. The Jobname will automatically be changed to Jobname_nn, (nn = 01 initially, and will be incremented each time EDSTART,3 is issued for subsequent full restarts). After the EDSTART command, you can input any commands needed to change the database. (Most commands which are applicable to an ANSYS LS-DYNA new analysis are also applicable to full restart analysis. A few commands related to contact specifications, initial velocity definitions, and adaptive meshing are not supported.) Then issue the EDIS command to specify which portions of the model should be initialized in the full restart using results data from the d3dumpnn file. Finally, issue the SOLVE command. At this point, new results files, Jobname_nn.RST and Jobname_nn.HIS, will be created. Time and output intervals in the new results files are continuous from the previous results files; the time is not reset to zero. (See A Full Restart in the ANSYS LS-DYNA User's Guide for a complete description of a full restart analysis.)

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
