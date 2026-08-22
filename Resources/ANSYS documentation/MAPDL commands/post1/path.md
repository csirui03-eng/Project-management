---
apdl: "PATH"
method: path
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.path
generated: 2026-08-22
tags: [mapdl-command]
---

# PATH

PyMAPDL: `mapdl.path(name='', npts='', nsets='', ndiv='', **kwargs)`

Defines a path name and establishes parameters for the path.

## Parameters

**name**: Name for this path (eight characters maximum. If `nPts` is blank, set the current path to the path with this name. If `nPts` is greater than zero, create a path of this name. If a path with this name already exists, replace it with a new path. If the `NAME` value is STATUS, display the status for path settings.

**npts**: The number of points used to define this path. The minimum number is two, and the maximum is 1000. Default is 2.

**nsets**: The number of sets of data which you can map to this path. You must specify at least four: X, Y, Z, and S. Default is 30.

**ndiv**: The number of divisions between adjacent points. Default is 20. There is no maximum number of divisions.

## Notes

The **PATH** command is used to define parameters for establishing a path. The path geometry is created by the [[ppath|PPATH]] command. Multiple paths may be defined and named; however, only one path may be active for data interpolation ( [[pdef|PDEF]] ) and data operations ( [[pcalc|PCALC]], etc.). Path geometry points and data are stored in memory while in POST1. If you leave POST1, the path information is erased. Path geometry and data may be saved in a file by archiving the data using the [[pasave|PASAVE]] command. Path information may be restored by retrieving the data using the [[paresu|PARESU]] command.

For overlapping nodes, the lowest numbered node is assigned to the path.

The number of divisions defined using `nDiv` does NOT affect the number of divisions used by [[plsect|PLSECT]] and [[prsect|PRSECT]].

For information on displaying paths you have defined, see [Mapping Results onto a Path](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_3.html#basdelepathtlm51799)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PATH.html
