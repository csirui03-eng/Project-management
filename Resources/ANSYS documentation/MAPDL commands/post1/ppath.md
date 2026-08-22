---
apdl: "PPATH"
method: ppath
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.ppath
generated: 2026-08-22
tags: [mapdl-command]
---

# PPATH

PyMAPDL: `mapdl.ppath(point='', node='', x='', y='', z='', cs='', **kwargs)`

Defines a path by picking or defining nodes, or locations on the currently active working plane, or by entering specific coordinate locations.

## Parameters

**point**: The point number. It must be greater than zero and less than or equal to the `nPts` value specified on the [[path|PATH]] command if graphical picking is not being used.

**node**: The node number defining this point. If blank, use the X, Y, Z coordinates to define the point. A valid node number will override `X`, `Y`, `Z` coordinate arguments.

**x**, **y**, **z**: The location of the point in the global Cartesian coordinate system. Use these arguments only if you omit the `NODE` argument.

**cs**: The coordinate system for interpolation of the path between the previous point and this point. Omit this argument if you wish to use the currently active ( [[csys|CSYS]] ) coordinate system. If the coordinate system of two adjacent points is different, the `CS` value of the latter point will be used.

## Notes

For linearized stress calculations, the path must be defined with nodes.

This command is designed and works best in interactive (GUI) mode, using the menu paths listed below. For command line operations, issue **PPATH**,P to define your path by picking nodes.

For information on displaying paths you have defined, see [Mapping Results onto a Path](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_3.html#basdelepathtlm51799)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PPATH.html
