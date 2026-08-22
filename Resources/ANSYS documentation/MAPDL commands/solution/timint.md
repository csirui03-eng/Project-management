---
apdl: "TIMINT"
method: timint
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.timint
generated: 2026-08-22
tags: [mapdl-command]
---

# TIMINT

PyMAPDL: `mapdl.timint(key='', lab='', **kwargs)`

Turns on transient effects.

## Parameters

**key**

Transient effects key:

- `OFF` - No transient effects (static or steady-state).
- `ON` - Include transient (mass or inertia) effects.

**lab**

Degree of freedom label:

- `ALL` - Apply this key to all appropriate labels (default).
- `STRUC` - Apply this key to structural DOFs.
- `THERM` - Apply this key to thermal DOFs.
- `ELECT` - Apply this key to electric DOFs.
- `MAG` - Apply this key to magnetic DOFs.
- `FLUID` - Apply this key to fluid DOFs.
- `DIFFU` - Apply this key to concentration of DOFs.

## Notes

Indicates whether this load step in a full transient analysis should use time integration, that is, whether it includes transient effects (e.g. structural inertia, thermal capacitance) or whether it is a static (steady-state) load step for the indicated DOFs. Transient initial conditions are introduced at the load step having `Key` = ON. Initial conditions are then determined from the previous two substeps. Zero initial velocity and acceleration are assumed if no previous substeps exist. See the [Structural Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_enercalc_app.html), the [Thermal Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/Hlp_G_THE4.html), and the [Low- Frequency Electromagnetic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_lof/Hlp_G_ELE16.html) for details.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TIMINT.html
