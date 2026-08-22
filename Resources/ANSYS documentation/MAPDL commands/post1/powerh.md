---
apdl: "POWERH"
method: powerh
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.magnetics_calculations.MagneticsCalculations.powerh
generated: 2026-08-22
tags: [mapdl-command]
---

# POWERH

PyMAPDL: `mapdl.powerh(**kwargs)`

Calculates the rms power loss in a conductor or lossy dielectric.

## Notes

**POWERH** invokes a Mechanical APDL macro which calculates the time-averaged (rms) power loss in a conductor or lossy dielectric material from a harmonic analysis. The power loss is stored in the parameter PAVG.

Conductor losses include solid conductors and surface conductors approximated by impedance or shielding boundary conditions. The power-loss density for solid conductors or dielectrics is stored in the element table with the label PLOSSD and may be listed ( [[pretab|PRETAB]] ) or displayed ( [[pletab|PLETAB]] ). PLOSSD does not include surface losses.

The elements of the conducting region must be selected before this command is issued.

**POWERH** is valid for 2D and 3D analyses.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_POWERH.html
