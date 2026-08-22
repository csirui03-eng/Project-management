---
apdl: "ANCYC"
method: ancyc
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.animation.Animation.ancyc
generated: 2026-08-22
tags: [mapdl-command]
---

# ANCYC

PyMAPDL: `mapdl.ancyc(numframes='', kcycl='', delay='', **kwargs)`

Applies a traveling wave animation to graphics data in a modal cyclic symmetry analysis.

**Command default:**

The default **ANCYC** command (issuing the command with no arguments) specifies these implicit argument values: **ANCYC**, 18, 0, 0.1

## Parameters

**numframes**: The number of plot frames for the animation. Valid values range from 5 through 36. The default is 18. A low value (because it specifies fewer graphical frames) produces a rougher animation but loads faster. A high value produces a smoother animation but requires more time to load.

**kcycl**

The animation mode:

- `0` - Continuous animation cycle (forward-reverse-forward).
- `1` - Discontinuous animation cycle (forward-reset-forward). This option is the default.

**delay**: The time delay (in seconds) between animation frames. Valid values range from 0.1 through 1.0. The default is 0.1 seconds, which produces a seemingly real-time animation. A higher value produces a slower animation.

## Notes

The **ANCYC** command is valid in a [modal cyclic symmetry analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycmodalans.html#cycsym_postproc_modal) only.

The command animates the cyclic symmetry mode shape plot in the General Post Processor ( [[post1|/POST1]] ). When you issue a nodal- or element-results plot command (for example, [[plnsol|PLNSOL]], [[plesol|PLESOL]], or [[pldisp|PLDISP]] ) and then issue the **ANCYC** command, Mechanical APDL applies a traveling wave animation to the mode shape plot.

Each frame of the animation is created by expanding the cyclic symmetry mode shape at increasing phase angles (via the [[cycexpand|/CYCEXPAND]] command) starting at zero in equal increments over 360°. The phase-angle increment is 360 / `NUMFRAMES`.

The animation display shows the traveling wave of the result quantity being plotted. The traveling wave animation is applicable only to nodal diameters (harmonic indices) greater than 0 and less than `N` / 2 (where `N` is the number of cyclic sectors in the model).

For more information, see [Applying a Traveling Wave Animation to the Cyclic Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycmodalans.html#gadvcyctwave) in the [Cyclic Symmetry Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/cycsym_example.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANCYC.html
