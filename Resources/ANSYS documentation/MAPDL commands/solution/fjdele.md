---
apdl: "FJDELE"
method: fjdele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_forces.FeForces.fjdele
generated: 2026-08-22
tags: [mapdl-command]
---

# FJDELE

PyMAPDL: `mapdl.fjdele(elem='', lab='', **kwargs)`

Deletes forces (or moments) on the components of the relative motion of a joint element.

## Parameters

**elem**: Element number, or ALL. (leaving this blank defaults to ALL)

**lab**

Valid labels are:

- `FX` - Force in local x direction.
- `FY` - Force in local y direction.
- `FZ` - Force in local z direction.
- `MX` - Moment about local x axis.
- `MY` - Moment about local y axis.
- `MZ` - Moment about local z axis.
- `ALL, or (blank)` - Delete all valid forces or moments.

## Notes

Valid for `MPC184` (joint options in KEYOPT(1)).

See [[fj|FJ]] for information on specifying forces (or moments).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FJDELE.html
