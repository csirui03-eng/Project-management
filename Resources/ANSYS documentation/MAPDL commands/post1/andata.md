---
apdl: "ANDATA"
method: andata
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.animation.Animation.andata
generated: 2026-08-22
tags: [mapdl-command]
---

# ANDATA

PyMAPDL: `mapdl.andata(delay='', ncycl='', rsltdat='', min_='', max_='', incr='', frclst='', autocont='', autocntr='', **kwargs)`

Displays animated graphics data for nonlinear problems.

## Parameters

**delay**: Time delay during animation (defaults to 0.5 seconds).

**ncycl**: Number of animation cycles (defaults to 5). Available in non-UI mode only.

**rsltdat**

The type of results data to be used for the animation sequence. This can be:

- `0` - Current load step data (default).
- `1` - Range of load step data.
- `2` - Range of results data.

**min_**: The range minimum value. If left blank or 0, defaults to the first data point.

**max_**: The range maximum value. If left blank or 0, defaults to the last data point.

**incr**: The increment between result data (defaults to 1).

**frclst**: Key to force the last sub step in a selected load step to be included in the animation (defaults to 0).

**autocont**: A value of 1 enables automatic scaling of contour values based on the overall subset range of values. The default value is 0 (no automatic scaling).

**autocntr**: A value of 1 disables automatic centering of displaced plots. The default value is 0 (allow automatic centering).

## Notes

Use the **ANDATA** command to create animations for nonlinear problems. The command works by displaying an individual graphical image for each result data set from the results file. For information about creating animations for linear problems, see the [[anim|ANIM]] command.

The command operates only on graphic display platforms supporting the [[seg|/SEG]] command. It uses a macro to produce an animation based on the last plot action command (for example, [[pldisp|PLDISP]] ).

The results file must have more than one set of results.

The command implicitly issues [[slashdscale|/DSCALE]], 1 for default displacement scaling. Large displacements may not give good results.

This command functions only in the postprocessor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANDATA.html
