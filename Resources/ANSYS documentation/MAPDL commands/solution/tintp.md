---
apdl: "TINTP"
method: tintp
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.tintp
generated: 2026-08-22
tags: [mapdl-command]
---

# TINTP

PyMAPDL: `mapdl.tintp(gamma='', alpha='', delta='', theta='', oslm='', tol='', avsmooth='', alphaf='', alpham='', **kwargs)`

Defines transient integration parameters.

## Parameters

**gamma**

Amplitude decay factor for 2nd order transient integration, for example, structural dynamics (used only if `ALPHA`, `DELTA`, `ALPHAF`, and `ALPHAM` are blank). Defaults to 0.005.

Alternatively, you can input the application type for the analysis using one of the following labels. In this case, the program automatically sets the transient dynamic solver algorithm and settings based on the intended application. For more information, see.

- `IMPA` - Impact application.
- `HISP` - High speed dynamic application.
- `MOSP` - Moderate speed dynamic application.
- `LOSP` - Low speed dynamic application.
- `QUAS` - Quasi-static application.

**alpha**: 2nd order transient integration parameter (used only if `GAMMA` is blank). Defaults to 0.2525.

**delta**: 2nd order transient integration parameter (used only if `GAMMA` is blank). Defaults to 0.5050.

**theta**: 1st order transient (for example, thermal transient) integration parameter. Defaults to 1.0

**oslm**: Specifies the oscillation limit criterion for automatic time stepping of 1st order transients (for example, thermal transients). Defaults to 0.5 with a tolerance of `TOL`.

**tol**: Tolerance applied to `OSLM`. Defaults to 0.0.

**avsmooth**

Smoothing flag option:

- `0` - Include smoothing of the velocity (1st order system) or the acceleration (2nd order system) (default).
- `1` - Do not include smoothing.

**alphaf**: Interpolation factor in HHT algorithm for force and damping terms (used only if `GAMMA` is blank). Defaults to 0.005.

**alpham**: Interpolation factor in HHT algorithm for inertial term (used only if `GAMMA` is blank). Defaults to 0.0.

## Notes

Used to define the transient integration parameters. For more information on transient integration parameters, refer to [Transient Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc2.html#anpdescp1order)

For structural transient analyses, you may choose between the Newmark and HHT time integration methods (see the [[trnopt|TRNOPT]] command). In this case, if `GAMMA` is input and the integration parameters `ALPHA`, `DELTA`, `ALPHAF`, and `ALPHAM` are left blank, the program will calculate the integration parameters. Alternatively, you can input these integration parameters directly on this command. However, for the unconditional stability and second order accuracy of the time integration, these parameters should satisfy a specific relationship, as described in [Description of Structural and Other Second Order Systems](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc2.html#anpsolu)

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TINTP.html
