---
apdl: "FL"
method: fl
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1._fatigue.Fatigue.fl
generated: 2026-08-22
tags: [mapdl-command]
---

# FL

PyMAPDL: `mapdl.fl(nloc='', node='', scfx='', scfy='', scfz='', title='', **kwargs)`

Defines a set of fatigue location parameters.

## Parameters

**nloc**: Reference number for this location (within `MXLOC` ). When defining a new location, defaults to lowest unused location. If the specified `NODE` is already associated with a location, `NLOC` defaults to that existing location.

**node**: Node number corresponding to this location (must be unique). Used only to associate a node with a new location or to find an existing location (if `NLOC` is not input). If `NODE` = -1 (or redefined), erase all parameters and fatigue stresses for this location.

**scfx**, **scfy**, **scfz**: Stress concentration factors applied to the total stresses. Factors are applied in the global X, Y, and Z directions unless the axisymmetric option of the [[fssect|FSSECT]] is used (that is, `RHO` is nonzero), in which case the factors are applied in the section x, y, and z (radial, axial, and hoop) directions.

**title**: User-defined title for this location (up to 20 characters).

## Notes

Repeat FL command to define additional sets of location parameters ( `MXLOC` limit), to redefine location parameters, or to delete location stress conditions.

One location must be defined for each node of interest and only one node can be associated with each location. See the FTSIZE command for the maximum locations ( `MXLOC` ) allowed. A location will be automatically defined for a node not having a location when the FSSECT, FSNODE, or FS command is issued. Automatically defined locations are assigned the lowest available location number, unity stress concentration factors, and no title.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FL.html
