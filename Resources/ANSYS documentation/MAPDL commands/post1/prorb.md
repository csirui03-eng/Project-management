---
apdl: "PRORB"
method: prorb
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.prorb
generated: 2026-08-22
tags: [mapdl-command]
---

# PRORB

PyMAPDL: `mapdl.prorb(whrlnodkey='', **kwargs)`

Prints the orbital motion characteristics of a rotating structure

## Parameters

**whrlnodkey**

Flag to print the whirl for each node:

- `1 (ON or YES)` - Print the whirl for each node.
- `0 (OFF or NO)` - No printout. This value is the default.

## Notes

When a structure is rotating and the Coriolis or gyroscopic effect is taken into account ( [[coriolis|CORIOLIS]] ), nodes lying on the rotation axis generally exhibit an elliptical orbital motion. The **PRORB** command prints out the [orbit](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/Hlp_G_ROTTERMINOLOGY.html#rotgloss1) characteristics A, B, PSI, PHI, YMAX, ZMAX, and Whirl of each rotating node, where

- A is the semi-major axis.
- B is the semi-minor axis.
- PSI is the angle between local y axis and major axis.
- PHI is the angle between initial position (t = 0) and major axis.
- YMAX is the maximum displacement along local y axis.
- ZMAX is the maximum displacement along local z axis.
- Whirl is the direction of an orbital motion (BW for backward whirl and FW for forward whirl).

Angles PSI and PHI are in degrees and within the range of -180 through +180.

To display the characteristics of the orbital path traversed by each node, issue the [[plorb|PLORB]] command.

The **PRORB** command is valid for line elements (such as `BEAM188`, `BEAM189`, `PIPE288`, and `PIPE289` ). **PRORB** is not supported for beam elements with the warping degree of freedom activated.

Your model must also involve a rotational velocity ( [[omega|OMEGA]] or [[cmomega|CMOMEGA]] ) with Coriolis enabled ( [[coriolis|CORIOLIS]] ).

Because orbit data is written in the database, a [[set|SET]] command must be issued after the **PRORB** command to ensure proper output for subsequent postprocessing commands.

The coordinate system for displaying nodal results must be global Cartesian ( [[rsys|RSYS]], `KCN` = 0). **PRORB** is not supported if nodes are rotated in a cylindrical coordinate system.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRORB.html
