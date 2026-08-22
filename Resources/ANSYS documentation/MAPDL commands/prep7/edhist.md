---
apdl: "EDHIST"
method: edhist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edhist
generated: 2026-08-22
tags: [mapdl-command]
---

# EDHIST

PyMAPDL: `mapdl.edhist(comp='', **kwargs)`

Specifies time-history output for an explicit dynamic analysis.

## Parameters

**comp**: Name of the component containing nodes or elements for which output is desired. Comp is required.

## Notes

The time-history output is written to the file Jobname.HIS. Output is written only for the nodes or elements contained in Comp. The data is written at time intervals specified on the EDHTIME command. If no time interval is specified, output is written at 1000 steps over the analysis. (See also the EDOUT command which controls time-history output in ascii form for an explicit dynamics analysis.)

Use EDHIST,LIST to list the time-history output specification. (The listing will include output requested with the EDOUT command.) Use EDHIST,DELE to delete the time-history output specification.

Jobname.HIS is a binary file that is read by the ANSYS time-history postprocessor (POST26). If LS-DYNA output has been requested on the EDWRITE command \[EDWRITE,LSDYNA or EDWRITE,BOTH\], the file D3THDT will also be written. D3THDT is a binary file that is read by the LS-POST postprocessor.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
