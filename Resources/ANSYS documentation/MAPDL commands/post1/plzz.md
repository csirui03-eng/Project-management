---
apdl: "PLZZ"
method: plzz
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.plzz
generated: 2026-08-22
tags: [mapdl-command]
---

# PLZZ

PyMAPDL: `mapdl.plzz(rotvel='', deltarotvel='', **kwargs)`

Plots the interference diagram from a cyclic modal analysis.

## Parameters

**rotvel**: Rotational speed in revolutions per minute (RPM) used to define the speed line. If blank, use the rotational speed (from [[omega|OMEGA]] ) specified in the prestressing step of the linear perturbation analysis. If explicitly input as 0, or if the linear perturbation was not used, no speed lines are plotted.

**deltarotvel**: Adds speed lines about the `RotVel` speed line corresponding to `RotVel` ± `DeltaRotVel`. Only plotted if `RotVel` is known.

## Notes

**PLZZ** plots the cyclic modal frequencies as points on a frequency vs. harmonic index (nodal diameter) graph. If rotational speed ( `RotVel` ) is provided, the speed line is also plotted, leading to the interference diagram (also known as the SAFE or ZZENF diagram). If `DeltaRotVel` is also provided, two additional speed lines are plotted, enveloping the safe speed line itself.

For more information, see [Postprocessing a Modal Cyclic Symmetry Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycmodalans.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLZZ.html
