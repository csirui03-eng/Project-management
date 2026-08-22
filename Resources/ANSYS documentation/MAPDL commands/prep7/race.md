---
apdl: "RACE"
method: race
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.race
generated: 2026-08-22
tags: [mapdl-command]
---

# RACE

PyMAPDL: `mapdl.race(xc='', yc='', rad='', tcur='', dy='', dz='', cname='', **kwargs)`

Defines a "racetrack" current source.

## Parameters

**xc**: Location of the mid-thickness of the vertical leg along the working plane X-axis.

**yc**: Location of the mid-thickness of the horizontal leg along the working plane Y-axis.

**rad**: Radius of curvature of the mid-thickness of the curves in the racetrack source. Defaults to.501 \* DY

**tcur**: Total current, amp-turns (MKS), flowing in the source.

**dy**: In-plane thickness of the racetrack source.

**dz**: Out-of-plane thickness (depth) of the racetrack source.

**cname**



## Notes

**RACE** invokes a Mechanical APDL macro which defines a racetrack current source in the working plane coordinate system.

(figure omitted, see the Ansys help page)

The current source is generated from bar and arc source primitives using `SOURC36` (which is assigned the next available element type number).

The macro is valid for use in 3D magnetic field analysis using a scalar potential formulation.

Current flows in a counterclockwise direction with respect to the working plane.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RACE.html
