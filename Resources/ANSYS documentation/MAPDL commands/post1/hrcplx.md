---
apdl: "HRCPLX"
method: hrcplx
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.set_up.SetUp.hrcplx
generated: 2026-08-22
tags: [mapdl-command]
---

# HRCPLX

PyMAPDL: `mapdl.hrcplx(loadstep='', substep='', omegat='', firstlcase='', secondlcase='', **kwargs)`

Computes and stores in the database the time-harmonic solution at a prescribed phase angle.

## Parameters

**loadstep**: Load step number of the data set to be read (defaults to 1).

**substep**: Substep number within `LOADSTEP`.

**omegat**

Angle in degrees (Ω (angle) times T (time)).

- If ≥ 360°, the amplitude is supplied.
- All others supply results at that angle. For example, if the angle is set to 0.0°, the real part of the solution is supplied. If the angle is set to -90° the imaginary part of the solution is supplied.

**firstlcase**: First load case number (defaults to 1).

**secondlcase**: Second load case number (defaults to 2).

## Notes

**HRCPLX** invokes a macro that combines the real and imaginary parts of the solution. If the angle is specified, it produces the following:

(equation not available in the PyMAPDL source, see the Ansys help page)

R<sub>R</sub> and R<sub>I</sub> are, respectively, the real and imaginary parts of the results quantity (e.g. the nodal displacements, the reaction forces,...).

α is the angle (OMEGAT).

`1STLCASE` and `2NDLCASE` are internally generated load cases. You may want to specify these to avoid overwriting an existing load case number 1 or 2.

Not all results computed by this command are valid. See [Summable, Non-Summable and Constant Data](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_4.html#apQ8Hn357ctg) in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for more information. When the amplitude of the solution is requested ( `OMEGAT` \>= 360°), averaged values (such as the nodal component stresses, which are an average of element nodal component stresses) are calculated by averaging the amplitudes. Because the degrees of freedom results have different phases, derived results (such as the equivalent stress SEQV) are not valid. See [POST1 and POST26 - Complex Results Postprocessing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_post15.html#thyeq1cdmplxres6a)

For postprocessing amplitudes, the only appropriate coordinate system is the solution coordinate system ( [[rsys|RSYS]],SOLU). When displaying the displacement amplitudes, use a contour display ( [[plnsol|PLNSOL]] command). Because a deformed shape display ( [[pldisp|PLDISP]] command) could lead to a non-physical shape, the displacement scaling is off by default ( [[slashdscale|/DSCALE]],,OFF).

For postprocessing cylindrical geometry, it is suggested that you rotate the element coordinate systems into the appropriate cylindrical system ( `EMODIF,,ESYS` ) before running the solution and then view the results in this system ( `RSYS,SOLU` ) in POST1.

Since **HRCPLX** performs load case combinations, it alters most of the data in the database. In particular, it alters applied loads such as forces and imposed displacements. To restore the original loads in the database for a subsequent analysis, reissue the [[set|SET]] command in POST1 to retrieve the real and imaginary set data.

To animate the solution over one period, use the [[anharm|ANHARM]] command.

`OMEGAT` is not equal to the phase shift.

This command is not supported after a cyclic symmetry analysis; use [[cycexpand|/CYCEXPAND]],,PHASEANG instead.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HRCPLX.html
