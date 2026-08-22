---
apdl: "TRANSFER"
method: transfer
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.transfer
generated: 2026-08-22
tags: [mapdl-command]
---

# TRANSFER

PyMAPDL: `mapdl.transfer(kcnto='', inc='', node1='', node2='', ninc='', **kwargs)`

Transfers a pattern of nodes to another coordinate system.

## Parameters

**kcnto**: Reference number of coordinate system where the pattern is to be transferred. Transfer occurs from the active coordinate system.

**inc**: Increment all nodes in the given pattern by `INC` to form the transferred node pattern.

**node1**, **node2**, **ninc**: Transfer nodes from pattern beginning with `NODE1` to `NODE2` (defaults to `NODE1` ) in steps of `NINC` (defaults to 1). If `NODE1` = ALL, `NODE2` and `NINC` are ignored and the pattern is all selected nodes ( [[nsel|NSEL]] ). If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component may be substituted for `NODE1` ( `NODE2` and `NINC` are ignored).

## Notes

Transfers a pattern of nodes from one coordinate system to another. Coordinate systems may be translated and rotated relative to each other. Initial pattern may be generated in any coordinate system. Coordinate values are interpreted in the active coordinate system and are transferred directly.

A model generated in one coordinate system may be transferred to another coordinate system. The user may define several coordinate systems (translated and rotated from each other), generate a model in one coordinate system, and then repeatedly transfer the model to other coordinate systems. The model may be generated in any type of coordinate system (Cartesian, cylindrical, etc.) and transferred to any other type of coordinate system. Coordinate values (X, Y, Z, or R, θ, Z, or etc.) of the model being transferred are interpreted in the active coordinate system type, regardless of how they were generated. Values are transferred directly and are interpreted according to the type of coordinate system being transferred to. For example, transferring from a Cartesian coordinate system to a cylindrical coordinate system (not recommended) would cause X = 2.0 and Y = 3.0 values to be directly interpreted as R = 2.0 and θ = 3.0 values, respectively.

This command is also valid in the [[slashmap|/MAP]] processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TRANSFER.html
