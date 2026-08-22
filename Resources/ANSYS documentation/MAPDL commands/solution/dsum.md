---
apdl: "DSUM"
method: dsum
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.dsum
generated: 2026-08-22
tags: [mapdl-command]
---

# DSUM

PyMAPDL: `mapdl.dsum(signif='', label='', td='', forcetype='', **kwargs)`

Specifies the double sum mode combination method.

## Parameters

**signif**: Combine only those modes whose significance level exceeds the `SIGNIF` threshold. For single point, multipoint, or DDAM response ( [[spopt|SPOPT]], SPRS, MPRS, or DDAM), the significance level of a mode is defined as the mode coefficient divided by the maximum mode coefficient of all modes. Any mode whose significance level is less than `SIGNIF` is considered insignificant and is not contributed to the mode combinations. The higher the `SIGNIF` threshold, the fewer the number of modes combined. `SIGNIF` defaults to 0.001. If `SIGNIF` is specified as 0.0, it is taken as 0.0. (This mode combination method is not valid for [[spopt|SPOPT]], PSD.)

**label**

Label identifying the combined mode solution output.

- `DISP` - Displacement solution (default). Displacements, stresses, forces, etc., are available.
- `VELO` - Velocity solution. Velocities, "stress velocities," "force velocities," etc., are available.
- `ACEL` - Acceleration solution. Accelerations, "stress accelerations," "force accelerations," etc., are available.

**td**: Time duration for earthquake or shock spectrum. `TD` defaults to 10.

**forcetype**

Label identifying the forces to be combined:

- `STATIC` - Combine the modal static forces (default).
- `TOTAL` - Combine the modal static plus inertial forces.

## Notes

This command is also valid for PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DSUM.html
