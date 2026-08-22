---
apdl: "NRLSUM"
method: nrlsum
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.nrlsum
generated: 2026-08-22
tags: [mapdl-command]
---

# NRLSUM

PyMAPDL: `mapdl.nrlsum(signif='', label='', labelcsm='', forcetype='', **kwargs)`

Specifies the Naval Research Laboratory (NRL) sum mode combination method.

## Parameters

**signif**: Combine only those modes whose significance level exceeds the `SIGNIF` threshold. For single point, multipoint, or DDAM response ( [[spopt|SPOPT]],SPRS, MPRS or DDAM), the significance level of a mode is defined as the mode coefficient divided by the maximum mode coefficient of all modes. Any mode whose significance level is less than `SIGNIF` is considered insignificant and is not contributed to the mode combinations. The higher the `SIGNIF` threshold, the fewer the number of modes combined. `SIGNIF` defaults to 0.001. If `SIGNIF` is specified as 0.0, it is taken as 0.0. (This mode combination method is not valid for [[spopt|SPOPT]],PSD.)

**label**

Label identifying the combined mode solution output.

- `DISP` - Displacement solution (default). Displacements, stresses, forces, etc., are available.
- `VELO` - Velocity solution. Velocities, "stress velocities," "force velocities," etc., are available.
- `ACEL` - Acceleration solution. Accelerations, "stress accelerations," "force accelerations," etc., are available.

**labelcsm**

Label identifying the CSM (Closely Spaced Modes) method.

- `CSM` - Use the CSM method.
- `` - Do not use the CSM method (default).

**forcetype**

Label identifying the forces to be combined:

- `STATIC` - Combine the modal static forces (default).
- `TOTAL` - Combine the modal static plus inertial forces.

## Notes

This command is also valid in PREP7. This mode combination method is usually used for [[spopt|SPOPT]],DDAM.

This CSM method is only applicable in a DDAM analysis ( [[spopt|SPOPT]], `DDAM` ). Element results calculation based on modal element results ( `Elcalc` on [[spopt|SPOPT]] ) is not supported and is automatically reset for this method. The CSM method combines two closely spaced modes into one mode when their frequencies are within 10 percent of the common mean frequency and their responses are opposite in sign. The contribution of these closely spaced modes is then included in the NRL sum as a single effective mode. Refer to [Closely Spaced Modes (CSM) Method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc7.html#eqe88ee1e2-71f7-4a8d-910a-d28d1d27641b)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NRLSUM.html
