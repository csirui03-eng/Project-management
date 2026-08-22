---
apdl: "EDCURVE"
method: edcurve
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edcurve
generated: 2026-08-22
tags: [mapdl-command]
---

# EDCURVE

PyMAPDL: `mapdl.edcurve(option='', lcid='', par1='', par2='', **kwargs)`

Specifies data curves for an explicit dynamic analysis.

## Parameters

**option**

Label identifying the option to be performed.

ADD - Define a data curve (default). If Option = ADD, Par1 and Par2 must be  
previously defined array parameters.

DELE - Delete the specified data curve (LCID). If LCID is blank, all data curves are  
deleted. Par1 and Par2 are ignored for this option.

LIST - List defined data curve (LCID). If LCID is blank, all data curves are listed.  
Par1 and Par2 are ignored for this option.

PLOT - Plot defined data curve (LCID). If Option = PLOT, LCID must be previously  
defined with an EDCURVE command. Otherwise a warning message will report that LCID has not been defined. Par1 and Par2 are ignored for this option.

**lcid**: Data curve ID number (no default). Must be a positive integer.

**par1**: Name of user-defined array parameter that contains the abscissa values of the curve data (e.g., time, effective plastic strain, effective strain rate, displacement, etc.).

**par2**: Name of user-defined array parameter that contains the ordinate values of the curve data (e.g., damping coefficients, initial yield stress, elastic modulus, force, etc.) corresponding to the abscissa values in Par1.

## Notes

EDCURVE can be used to define material data curves (e.g., stress- strain) and load data curves (force-deflection) associated with material models in an explicit dynamics analysis. Material data specified by this command is typically required to define a particular material behavior (e.g., TB,HONEY), and the LCID number is used as input on the TBDATA command.

EDCURVE can also be used to define load curves that represent time dependent loads (force, displacement, velocity, etc.). Par1 must contain the time values, and Par2 must contain the corresponding load values. The LCID number assigned to the load curve can be used as input on the EDLOAD command.

Note:: : You cannot update a previously defined data curve by changing the array parameters that were input as Par1 and Par2. The data curve definition is written to the database at the time EDCURVE is issued. Therefore, subsequent changes to the array parameters that were used as input on EDCURVE will not affect the load curve definition. If you need to change the load curve definition, you must delete the load curve (EDCURVE,DELE,LCID) and define it again.

LCID identifies the data curve. If the value input for LCID is the same as the ID number for a data curve previously defined by EDCURVE, the previous data will be overwritten. Use EDCURVE,LIST and EDCURVE,PLOT to check existing data curves.

A starting array element number must be specified for Par1 and Par2. The input for these fields must be a single column array parameter, or a specific column from a multi-column array parameter. When using the GUI with multi-column parameters, you must specify the parameter name and starting position for Par1 and Par2 by typing the EDCURVE command in the Input Window. This is because only the parameter name is available through the dialog box, which pulls in the first position of a single-column array parameter.

If you need to change a curve definition in an explicit dynamic small restart analysis, issue EDSTART,2 first (to specify the restart), then issue the EDCURVE command. The revised curve must contain the same number of points as the curve it replaces. This limitation does not apply to a full restart analysis (EDSTART,3).

This command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
