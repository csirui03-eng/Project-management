---
apdl: "MMF"
method: mmf
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.magnetics_calculations.MagneticsCalculations.mmf
generated: 2026-08-22
tags: [mapdl-command]
---

# MMF

PyMAPDL: `mapdl.mmf(**kwargs)`

Calculates the magnetomotive force along a path.

## Notes

**MMF** invokes a Mechanical APDL macro which calculates the magnetomotive force (mmf) along a predefined path ( [[path|PATH]] ). It is valid for both 2D and 3D magnetic field analyses. The calculated mmf value is stored in the parameter MMF.

A closed path ( [[path|PATH]] ), passing through the magnetic circuit for which mmf is to be calculated, must be defined before this command is issued. A counterclockwise ordering of points on the [[ppath|PPATH]] command will yield the correct sign on the mmf. The mmf is based on Ampere's Law. The macro makes use of calculated values of field intensity (H), and uses path operations for the calculations. All path items are cleared upon completion. The **MMF** macro sets the "ACCURATE" mapping method and "MAT" discontinuity option of the [[pmap|PMAP]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MMF.html
