---
apdl: "BRANCH"
method: branch
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.piping.Piping.branch
generated: 2026-08-22
tags: [mapdl-command]
---

# BRANCH

PyMAPDL: `mapdl.branch(node='', x='', y='', z='', **kwargs)`

Defines the starting point for a piping branch.

## Parameters

**node**: Start branch at this node.

**x**, **y**, **z**: Start branch at this location (in the active coordinate system). Used only if `Node` is not input or input but the node itself is not previously defined. In either case a node is generated at this location and assigned the number `Node` (or 1 + previous maximum node number if `Node` is not input).

## Notes

Notes See the RUN command in [Archived Commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/Hlp_C_VALVE.html) for information about piping models.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BRANCH.html
