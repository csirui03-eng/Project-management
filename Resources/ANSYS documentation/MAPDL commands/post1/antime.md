---
apdl: "ANTIME"
method: antime
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.animation.Animation.antime
generated: 2026-08-22
tags: [mapdl-command]
---

# ANTIME

PyMAPDL: `mapdl.antime(nfram='', delay='', ncycl='', autocntrky='', rsltdat='', min_='', max_='', **kwargs)`

Generates a sequential contour animation over a range of time.

## Parameters

**nfram**: Number of frame captures (defaults to 5).

**delay**: Time delay during animation (defaults to 0.1 seconds).

**ncycl**: Number of animation cycles (defaults to 5). Available in non-UI mode only.

**autocntrky**: Auto-scales contour values, based on the overall subset range of values. The auto-scaling option defaults to 0, no auto-scaling.

**rsltdat**

The results data to be used for the animation sequence. This can be:

- `0` - Current load step data (default).
- `1` - Range of load step data.
- `2` - Range of time data.

**min_**: The range minimum value. If left blank defaults to the first data point.

**max_**: The range maximum value. If left blank defaults to the last data point.

## Notes

The **ANTIME** command operates only on graphic display platforms supporting the [[seg|/SEG]] command. It uses a Mechanical APDL macro to produce an animation of contour values for the last plot action command (for example, [[pldisp|PLDISP]] ). After executing **ANTIME**, the [[anim|ANIM]] command replays the animated sequence.

This command functions only in the postprocessor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANTIME.html
