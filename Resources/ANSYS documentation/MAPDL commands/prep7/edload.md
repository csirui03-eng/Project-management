---
apdl: "EDLOAD"
method: edload
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edload
generated: 2026-08-22
tags: [mapdl-command]
---

# EDLOAD

PyMAPDL: `mapdl.edload(option='', lab='', key='', cname='', par1='', par2='', phase='', lcid='', scale='', btime='', dtime='', **kwargs)`

Specifies loads for an explicit dynamics analysis.

## Parameters

**option**

Label identifying the load option to be performed.

ADD - Define a load (default). If Option = ADD, Cname must be a valid node or element  
component name (or PART number). You must also specify a load curve using Par1 and Par2 (previously defined array parameters) or LCID (a previously defined load curve).

DELE - Delete specified load. If Lab and Cname are blank, all loads are deleted. Par1,  
Par2, PHASE, and LCID are ignored for this option.

LIST - List specified load. If Lab and Cname are blank, all loads are listed. Par1,  
Par2, PHASE, and LCID are ignored for this option.

**lab**

Valid load labels for loads applied to nodes:

FX, FY, FZ - Forces.

MX, MY, MZ - Moments.

UX, UY, UZ - Displacements.

ROTX, ROTY, ROTZ - Rotations.

VX, VY, VZ - Velocities.

OMGX, OMGY, OMGZ - Angular velocities.

AX, AY, AZ - Accelerations (on nodes).

ACLX, ACLY, ACLZ - Base accelerations.

TEMP - Temperature.

**key**: When Lab = PRESS, KEY = Load key (face number) associated with a surface pressure load. Load keys (1,2,3, etc.) are listed under "Surface Loads" in the input data tables for each element type in the Element Reference.

**cname**: Name of existing component \[CM\] or PART number \[EDPART\] to which this load is to be applied. For all load labels except the pressure load (Lab = PRESS) and the rigid body loads (Lab = RBxx), the component must consist of nodes. For pressure loads, the component must consist of elements. For rigid body loads, a part number must be input instead of a component name. The part number must correspond to a set of elements that has been identified as a rigid body \[EDMP,RIGID,MAT\].

**par1**: Name of user-defined array parameter that contains the time values of the load.

**par2**: Name of user-defined array parameter that contains the "data" values of the load corresponding to the time values in Par1.

**phase**

Phase of the analysis in which the load curve is to be used.

0 - Curve is used in transient analysis only (default).

1 - Curve is used in stress initialization or dynamic relaxation only.

2 - Curve is used in both stress initialization (or dynamic relaxation) and  
transient analysis.

**lcid**: Data curve ID number representing the load curve to be applied. The load curve must have been previously defined using the EDCURVE command. If LCID is specified, Par1 and Par2 must be left blank (in the GUI, select "None" for Par1 and Par2).

**scale**: Load curve scale factor applied to the specified load curve. The scale value is applied to the data in Par2 or to the ordinate data in the load curve specified by LCID.

**btime**: Birth time, or time when imposed motion is activated. The default is 0.0. Some load types do not support birth and death time; see Table 132: Birth Time, Death Time, and CID Support in the Notes section for more information.

**dtime**: Death time, or time when imposed motion is removed. The default is 1 x 1038. Some load types do not support birth and death time; see Table 132: Birth Time, Death Time, and CID Support in the Notes section for more information.

## Notes

If a component name is input (Cname) and the specified component definition is changed before the SOLVE command, the last definition will be used.

You can specify the load data by inputting LCID (the ID number of a previously defined load curve) or by inputting the two array parameters Par1 and Par2 (which contain time and load values, respectively). The input for Par1 and Par2 may be a single column array parameter, or a specific column from a multi-column array parameter. A starting array element number can be specified for Par1 and Par2; if none is specified, array element 1 is used by default.
