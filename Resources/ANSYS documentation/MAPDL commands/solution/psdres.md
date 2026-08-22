---
apdl: "PSDRES"
method: psdres
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.psdres
generated: 2026-08-22
tags: [mapdl-command]
---

# PSDRES

PyMAPDL: `mapdl.psdres(lab='', relkey='', **kwargs)`

Controls solution output written to the results file from a PSD analysis.

**Command default:**

Relative displacement solution, no velocity or acceleration solution for 1 σ results.

## Parameters

**lab**

Label identifying the solution output:

- `DISP` - Displacement solution (default). One-sigma displacements, stresses, forces, etc. Written as load step 3 on `FileRST`.
- `VELO` - Velocity solution. One-sigma velocities, "stress velocities," "force velocities," etc. Written as load step 4 of `FileRST`.
- `ACEL` - Acceleration solution. One-sigma accelerations, "stress accelerations," "force accelerations," etc. Written as load step 5 on `FileRST`.

**relkey**

Key defining relative or absolute calculations:

- `REL` - Calculations are relative to the base excitation (default).
- `ABS` - Calculations are absolute.
- `OFF` - No calculation of solution output identified by `Lab`.

## Notes

Controls the amount and form of solution output written to the results file from a PSD analysis. One-sigma values of the relative or absolute displacement solution, relative or absolute velocity solution, relative or absolute acceleration solution, or any combination may be included on the results file.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSDRES.html
