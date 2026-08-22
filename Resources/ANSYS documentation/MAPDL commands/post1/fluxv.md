---
apdl: "FLUXV"
method: fluxv
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.magnetics_calculations.MagneticsCalculations.fluxv
generated: 2026-08-22
tags: [mapdl-command]
---

# FLUXV

PyMAPDL: `mapdl.fluxv(**kwargs)`

Calculates the flux passing through a closed contour.

## Notes

**FLUXV** invokes a Mechanical APDL macro which calculates the flux passing through a closed contour (path) predefined by [[path|PATH]].

The calculated flux is stored in the parameter FLUX.

In a 2D analysis, at least two nodes must be defined on the path. In 3D, a path of nodes describing a closed contour must be specified (that is, the first and last node in the path specification must be the same).

A counterclockwise ordering of nodes on the [[ppath|PPATH]] command gives the correct sign on flux.

Path operations are used for the calculations, and all path items are cleared upon completion.

This macro is available for vector potential formulations only.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FLUXV.html
