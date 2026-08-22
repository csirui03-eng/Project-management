---
apdl: "TRPOIN"
method: trpoin
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.trace_points.TracePoints.trpoin
generated: 2026-08-22
tags: [mapdl-command]
---

# TRPOIN

PyMAPDL: `mapdl.trpoin(x='', y='', z='', vx='', vy='', vz='', chrg='', mass='', **kwargs)`

Defines a point through which a charged particle trace will travel.

## Parameters

**x**, **y**, **z**: Coordinate location of the trace point (in the active coordinate system). If `X` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**vx**, **vy**, **vz**: Particle velocities in the X, Y and Z directions (in the active coordinate system).

**chrg**: Particle charge.

**mass**: Particle mass.

## Notes

Defines a point through which a charged particle trace ( [[pltrac|PLTRAC]] ) will travel. Multiple points (50 maximum) may be defined which will result in multiple particle traces. Use [[trplis|TRPLIS]] to list the currently defined trace points and [[trpdel|TRPDEL]] to delete trace points.

The VX, VY, VZ, CHRG, and MASS arguments only apply to charged particles.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TRPOIN.html
