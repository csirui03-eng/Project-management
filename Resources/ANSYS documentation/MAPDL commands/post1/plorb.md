---
apdl: "PLORB"
method: plorb
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.plorb
generated: 2026-08-22
tags: [mapdl-command]
---

# PLORB

PyMAPDL: `mapdl.plorb(**kwargs)`

Displays the orbital motion of a rotating structure

## Notes

When a structure is rotating and the Coriolis or gyroscopic effect is taken into account ( [[coriolis|CORIOLIS]] ), nodes lying on the rotation axis generally exhibit an elliptical orbital motion. The **PLORB** command displays the [orbit](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/Hlp_G_ROTTERMINOLOGY.html#rotgloss1) of each rotating node as well as the deformed shape at time t = 0 (the real part of the solution).

To print the characteristics of the orbital path traversed by each node, issue the [[prorb|PRORB]] command.

The **PLORB** command is valid for line elements (such as `BEAM188`, `BEAM189`, `PIPE288`, and `PIPE289` ). **PLORB** is not supported for beam elements with the warping degree of freedom activated.

Your model must also involve a rotational velocity ( [[omega|OMEGA]] or [[cmomega|CMOMEGA]] ) with Coriolis enabled ( [[coriolis|CORIOLIS]] ).

Because orbit data is written in the database, a [[set|SET]] command must be issued after the **PLORB** command to ensure proper output for subsequent postprocessing commands.

The coordinate system for displaying nodal results must be global Cartesian ( [[rsys|RSYS]], `KCN` = 0). **PLORB** is not supported if nodes are rotated in a cylindrical coordinate system.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLORB.html
