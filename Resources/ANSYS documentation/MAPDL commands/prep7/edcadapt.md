---
apdl: "EDCADAPT"
method: edcadapt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edcadapt
generated: 2026-08-22
tags: [mapdl-command]
---

# EDCADAPT

PyMAPDL: `mapdl.edcadapt(freq='', tol='', opt='', maxlvl='', btime='', dtime='', lcid='', adpsize='', adpass='', ireflg='', adpene='', adpth='', maxel='', **kwargs)`

Specifies adaptive meshing controls for an explicit dynamic analysis.

## Parameters

**freq**: Time interval between adaptive mesh refinements (default = 0.0). Use FREQ = STAT to list the current adaptive meshing control settings.

**tol**: Adaptive angle tolerance (in degrees) for which adaptive meshing will occur (default = 1e31). If the relative angle change between elements exceeds the specified tolerance value, the elements will be refined.

**opt**

Adaptivity option:

1 - Angle change (in degrees) of elements is based on original mesh configuration  
(default).

2 - Angle change (in degrees) of elements is incrementally based on previously  
refined mesh.

**maxlvl**: Maximum number of mesh refinement levels (default = 3). This parameter controls the number of times an element can be remeshed. Values of 1, 2, 3, 4, etc. allow a maximum of 1, 4, 16, 64, etc. elements, respectively, to be created for each original element.

**btime**: Birth time to begin adaptive meshing (default = 0.0).

**dtime**: Death time to end adaptive meshing (default = 1e31).

**lcid**: Data curve number (previously defined on the EDCURVE command) identifying the interval of remeshing (no default). The abscissa of the data curve is time, and the ordinate is the varied adaptive time interval. If LCID is nonzero, the adaptive frequency (FREQ) is replaced by this load curve. Note that a nonzero FREQ value is still required to initiate the first adaptive loop.

**adpsize**: Minimum element size to be adapted based on element edge length (default = 0.0).

**adpass**

One or two pass adaptivity option.

0 - Two pass adaptivity (default).

1 - One pass adaptivity.

**ireflg**: Uniform refinement level flag (no default). Values of 1, 2, 3, etc. allow 4, 16, 64, etc. elements, respectively, to be created uniformly for each original element.

**adpene**: Adaptive mesh flag for starting adaptivity when approaching (positive ADPENE value) or penetrating (negative ADPENE value) the tooling surface (default = 0.0).

**adpth**: Absolute shell thickness level below which adaptivity should begin. This option works only if the adaptive angle tolerance (TOL) is nonzero. If thickness based adaptive remeshing is desired without angle change, set TOL to a large angle. The default is ADPTH = 0.0, which means this option is not used.

**maxel**: Maximum number of elements at which adaptivity will be terminated (no default). Adaptivity is stopped if this number of elements is exceeded.

## Notes

The EDCADAPT command globally sets the control options for all part IDs that are to be adaptively meshed (see the EDADAPT command). Because FREQ defaults to zero, you must input a nonzero value in this field in order to activate adaptive meshing. You must also specify a reasonable value for TOL since the default adaptive angle tolerance (1e31) will not allow adaptive meshing to occur.

The EDCADAPT command is not supported in an explicit dynamic full restart analysis (EDSTART,3).

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
