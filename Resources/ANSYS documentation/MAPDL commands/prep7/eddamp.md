---
apdl: "EDDAMP"
method: eddamp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.eddamp
generated: 2026-08-22
tags: [mapdl-command]
---

# EDDAMP

PyMAPDL: `mapdl.eddamp(part='', lcid='', valdmp='', **kwargs)`

Defines mass weighted (Alpha) or stiffness weighted (Beta) damping for

an explicit dynamics model.

## Parameters

**part**: PART number \[EDPART\] identifying the group of elements to which damping should be applied. If PART = ALL (default), damping is applied to the entire model.

**lcid**: Load curve ID (previously defined with the EDCURVE command) identifying the damping coefficient versus time curve. If time- dependent damping is defined, an LCID is required.

**valdmp**: Constant system damping coefficient or a scale factor applied to the curve defining damping coefficient versus time.

## Notes

Mass-weighted (Alpha) or stiffness-weighted (Beta) damping can be defined with the EDDAMP command. Generally, stiffness proportional or beta damping is effective for oscillatory motion at high frequencies. This type of damping is orthogonal to rigid body motion and so will not damp out rigid body motion. On the other hand, mass proportional or alpha damping is more effective for low frequencies and will damp out rigid body motion. The different possibilities are described below:

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.

Mass-weighted or Alpha damping

When PART = (blank) or ALL (default), mass-weighted global damping can be defined in the following two ways. In this case, the same damping is applied for the entire structure.

When the damping coefficient versus time curve (LCID) is specified using the EDCURVE command, VALDMP is ignored by LS-DYNA (although it is written in the LS-DYNA input file Jobname.K). The damping force applied to each node in the model is given by fd = d(t)mv, where d(t) is the damping coefficient as a function of time defined by the EDCURVE command, m is the mass, and v is the velocity.

When the LCID is 0 or blank (default), a constant mass-weighted system damping coefficient can be specified using VALDMP.

The constant and time-dependent damping, described above, cannot be defined simultaneously. The last defined global damping will overwrite any previously defined global damping.

Mass-weighted or Alpha damping

When both a valid PART number is specified and the damping coefficient versus time curve (LCID) is specified using the EDCURVE command, mass- weighted time-dependent damping will be defined for the particular PART. In this case, VALDMP will act as a scaling factor for the damping versus time curve (if VALDMP is not specified, it will default to 1). A valid PART number must be specified to define this type of damping. For example, use PART =1 (and not blank) when the entire model consists of only one PART. Issue the command repeatedly with different PART numbers in order to specify alpha damping for different PARTS.

Stiffness-weighted or Beta damping

When a valid PART number is specified with LCID = 0 or (blank) (default), a stiffness-weighted (Beta) constant damping coefficient for this particular PART can be defined by VALDMP. The stiffness-weighted value corresponds to the percentage of damping in the high frequency domain. For example, 0.1 roughly corresponds to 10% damping in the high frequency domain. Recommended values range from 0.01 to 0.25. Values lower than 0.01 may have little effect. If a value larger than 0.25 is used, it may be necessary to lower the time step size significantly (see the EDCTS command). Issue the command repeatedly with different PART numbers in order to specify beta damping for different PARTS. Time-dependent stiffness-weighted damping is not available in ANSYS LS- DYNA.

The mass-weighted and stiffness-weighted damping, described above, cannot be defined simultaneously for a particular PART number. The last defined damping for the particular PART number will overwrite any previously defined mass-weighted or stiffness-weighted damping for this PART.

In order to define the mass-weighted and stiffness-weighted damping simultaneously, you can use the MP,BETD command (instead of the EDDAMP,PART, ,VALDMP command) to define stiffness-weighted (Beta) constant damping coefficient. However, do not use both of these commands together to define stiffness-weighted (Beta) constant damping coefficient for a particular PART. If you do, duplicate stiffness- weighted (Beta) constant damping coefficients for this PART will be written to the LS-DYNA input file Jobname.K. The last defined value will be used by LS-DYNA. Also, note that the MP,BETD command is applied on the MAT number, and not on the PART number. Since a group of elements having the same MAT ID may belong to more than one PART (the opposite is not true), you need to issue the MP,BETD command only once for this MAT ID and the stiffness-weighted (Beta) damping coefficients will be automatically defined for all the PARTs with that MAT ID.

Mass-weighted and stiffness-weighted damping can be defined simultaneously using the EDDAMP command only when mass-weighted damping (constant or time-dependent) is defined as global damping (EDDAMP, ALL, LCID, VALDMP) and stiffness-weighted damping is defined for all necessary PARTs (EDDAMP,PART, ,VALDMP).

To remove defined global damping, reissue the EDDAMP, ALL command with LCID and VALDMP set to 0. To remove damping defined for a particular PART, reissue EDDAMP, PART, where PART is the PART number, with LCID and VALDMP set to 0. There is no default for the EDDAMP command, i.e., issuing the EDDAMP command with PART = LCID = VALDMP = 0 will result in an error. Stiffness-weighted damping defined by the MP,BETD command can be deleted using MPDELE, BETD, MAT.

In an explicit dynamic small restart (EDSTART,2) or full restart analysis (EDSTART,3), you can only specify global alpha damping. This damping will overwrite any alpha damping input in the original analysis. If you do not input global alpha damping in the restart, the damping properties input in the original analysis will carry over to the restart.

Damping specified by the EDDAMP command can be listed, along with other explicit dynamics specifications, by typing the command string EDSOLV\$STAT into the ANSYS input window. Beta damping specified by the MP,BETD command can be listed by MPLIST, MAT command.

This command is also valid in PREP7.
