---
apdl: "EMF"
method: emf
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.magnetics_calculations.MagneticsCalculations.emf
generated: 2026-08-22
tags: [mapdl-command]
---

# EMF

PyMAPDL: `mapdl.emf(**kwargs)`

Calculates the electromotive force (emf), or voltage drop along a predefined path.

## Notes

**EMF** invokes a Mechanical APDL macro which calculates the electromotive force (emf), or voltage drop along a predefined path (specified with the [[path|PATH]] command). It is valid for both 2D and 3D electric field analysis. The calculated emf value is stored in the parameter EMF.

You must define a line path (via the [[path|PATH]] command) before issuing the **EMF** command macro. The macro uses calculated values of the electric field (EF), and uses path operations for the calculations. All path items are cleared when the macro finishes executing.

The **EMF** macro sets the "ACCURATE" mapping method and "MAT" discontinuity option on the [[pmap|PMAP]] command. The program retains these settings after executing the macro.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EMF.html
