---
apdl: "SPOINT"
method: spoint
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.spoint
generated: 2026-08-22
tags: [mapdl-command]
---

# SPOINT

PyMAPDL: `mapdl.spoint(node='', x='', y='', z='', inertiakey='', **kwargs)`

Defines a point for force/moment summations or inertia calculation

## Parameters

**node**: Node number of the desired point. If zero, use `X`, `Y`, `Z` to describe point.

**x**, **y**, **z**: Global Cartesian coordinates of the desired summation point. Used if `NODE` is 0. Defaults to (0,0,0).

**inertiakey**

Inertia key:

- `OFF` - Point or node is used for the force/moment summations (default).
- `ON` - Point or node is used for the calculation of total inertia.

## Notes

By default ( `InertiaKey` = OFF), defines a point (any point other than the origin) about which the tabular moment summations are computed. If force summations are desired in other than the global Cartesian directions, a node number must be specified on the `NODE` field, and the desired coordinate system must be activated with [[rsys|RSYS]]. The command must be issued in the [[post1|/POST1]] module.

When the inertia key is activated ( `InertiaKey` = ON), the total inertia printed in the precise mass summary is calculated with respect to the point or node in the global Cartesian system. In this case, the command must be issued during the first load step in the [[slashsolu|/SOLU]] module.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPOINT.html
