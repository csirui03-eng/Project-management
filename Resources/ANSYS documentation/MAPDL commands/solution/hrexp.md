---
apdl: "HREXP"
method: hrexp
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.hrexp
generated: 2026-08-22
tags: [mapdl-command]
---

# HREXP

PyMAPDL: `mapdl.hrexp(angle='', **kwargs)`

Specifies the phase angle for the harmonic analysis expansion pass.

## Parameters

**angle**: Phase angle (degrees) for expansion pass. If ALL (default), use both 0.0° (real) and 90.0° (imaginary) phase angles.

## Notes

Specifies the phase angle where the expansion pass will be done for a harmonic mode-superposition expansion pass.

For a specific angle, the following real solution is stored in the results (2.rst) file:

(equation not available in the PyMAPDL source, see the Ansys help page)

Where:

i is the degree of freedom number.

(equation omitted) is the amplitude of thei th degree of freedom solution

Φ <sup>i</sup> is the phase shift angle of the i th degree of freedom solution

ϕ is the supplied phase shift angle ( `ANGLE` )

If `ANGLE` is ALL, both the real and imaginary parts of the solution are stored in the results file.

For more details about the solution equations, see [Harmonic Analyses](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc4.html#anwaveloadingharm) in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html).

This command is ignored if the [[hropt|HROPT]] command has been issued with `Method` = KRYLOV, VT, or VTPA.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HREXP.html
