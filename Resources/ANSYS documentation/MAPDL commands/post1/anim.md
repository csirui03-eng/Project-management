---
apdl: "ANIM"
method: anim
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.animation.Animation.anim
generated: 2026-08-22
tags: [mapdl-command]
---

# ANIM

PyMAPDL: `mapdl.anim(ncycl='', kcycl='', delay='', **kwargs)`

Displays animated graphics data for linear problems.

## Parameters

**ncycl**: Number of cycles associated with the animation (defaults to 5 in non-GUI mode only)

**kcycl**

Animation mode:

- `0` - Continuous animation cycle (forward-reverse-forward-etc.) (default).
- `1` - Discontinuous animation cycle (forward-reset-forward-etc.).

**delay**: Time delay (seconds) between animation frames (defaults to 0.1 seconds).

## Notes

Use the **ANIM** command to create animations for linear problems only. The command uses the currently displayed picture based on one particular data set from the results file, and linearly interpolates that data into different sets, displaying pictures of each interpolated data set in sequence to create animation. For information about creating animations for nonlinear problems, see the [[andata|ANDATA]] command.

This command is device-dependent.

Do not resize the graphic while animation is in progress; doing so can result in distorted plots.

For more information, see the [[seg|/SEG]] command for details about segment storage, and the [[ancntr|ANCNTR]] macro for a convenient method of storing graphics frames in terminal memory segments.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANIM.html
