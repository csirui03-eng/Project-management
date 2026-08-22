---
apdl: "EDOUT"
method: edout
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edout
generated: 2026-08-22
tags: [mapdl-command]
---

# EDOUT

PyMAPDL: `mapdl.edout(option='', **kwargs)`

Specifies time-history output (ASCII format) for an explicit dynamics

analysis.

## Parameters

**option**

Output data option. Each option corresponds to a separate file that is written by the LS-DYNA solver. If Option = ALL, all files except NODOUT and ELOUT are written. Valid options are:

GLSTAT - Global data (default).

BNDOUT - Boundary condition forces and energy.

RWFORC - Wall force.

DEFORC - Discrete element data.

MATSUM - Material energies data.

NCFORC - Nodal interface forces.

RCFORC - Resultant interface force data.

DEFGEO - Deformed geometry data.

SPCFORC - SPC reaction force data.

SWFORC - Nodal constraint reaction force data (spotwelds and rivets).

RBDOUT - Rigid body data.

GCEOUT - Geometry contact entities.

SLEOUT - Sliding interface energy.

JNTFORC - Joint force data.

NODOUT - Nodal data.

ELOUT - Element data.

## Notes

This command specifies output to be written during an explicit dynamics solution. The data corresponding to each Option is written to a separate ASCII file having the same name as the Option label. The data is written for the entire model at time intervals specified by the EDHTIME command. If no time interval is specified, output is written at 1000 steps over the analysis. (See also the EDHIST command which specifies time-history output for a portion of the model.) The data written to the MATSUM file is actually for each PART number (EDPART) at time intervals specified by the EDHTIME command, but the data is listed following the Mat no. in the file.

For Option = NODOUT and ELOUT, you must specify a component; you must issue EDHIST before issuing EDOUT,NODOUT or EDOUT,ELOUT.

Use EDOUT,LIST to list the current time-history output specifications. (The listing will include output requested with the EDHIST command.) Use EDOUT,DELE to delete all output specifications that have been defined with the EDOUT command.

In order for the specified output files to be written, you must also request that explicit dynamics results be written to an LS-DYNA output file \[EDWRITE,LSDYNA or EDWRITE,BOTH\].

In an explicit dynamic small restart analysis (EDSTART,2) or full restart analysis (EDSTART,3), the same ASCII files that were requested for the original analysis are written by default for the restart. You can request different files by issuing the appropriate EDOUT commands in the restart analysis.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
