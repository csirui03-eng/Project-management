---
apdl: "EDSHELL"
method: edshell
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edshell
generated: 2026-08-22
tags: [mapdl-command]
---

# EDSHELL

PyMAPDL: `mapdl.edshell(wpan='', shnu='', shtc='', wpbt='', shpl='', itrst='', **kwargs)`

Specifies shell computation controls for an explicit dynamics analysis.

## Parameters

**wpan**: Maximum shell element warpage angle in degrees. Defaults to 20.

**shnu**

Hughes-Liu shell normal update option:

-2 - Unique nodal fibers. This option is required for SHELL163 (KEYOPT(1) = 1, 6, or  
7)  if the real constant NLOC = 1 or -1.

-1 - Compute normals each cycle (default). This option is recommended.

1 - Compute on restarts.

n - Compute every nth substep.

**shtc**

Shell thickness change option:

0 - No change.

1 - Membrane straining causes thickness change. Important in sheet metal forming  
(default).

**wpbt**

Warping stiffness option for Belytschko-Tsay shells:

1 - Belytschko-Wong-Chiang warping stiffness added. This option is recommended.

2 - Belytschko-Tsay warping stiffness (default).

**shpl**

Shell plasticity option. This option is only valid for these material models: strain rate independent plastic kinematic, strain rate dependent plasticity, power law plasticity, and piecewise linear plasticity.

1 - Iterative plasticity with 3 secant iterations (default).

2 - Full iterative plasticity.

3 - Radial return noniterative plasticity. (Use this option with caution; it may  
lead to inaccurate results.)

**itrst**

Triangular shell sorting option. If sorting is on, degenerate quadrilateral shell elements are treated as triangular shells.

1 - Full sorting (default).

2 - No sorting.

## Notes

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
