---
apdl: "KL"
method: kl
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.kl
generated: 2026-08-22
tags: [mapdl-command]
---

# KL

PyMAPDL: `mapdl.kl(nl1='', ratio='', nk1='', **kwargs)`

Generates a keypoint at a specified location on an existing line.

## Parameters

**nl1**: Number of the line. If negative, the direction of line (as interpreted for `RATIO` ) is reversed. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**ratio**: Ratio of line length to locate keypoint. Must be between 0.0 and 1.0. Defaults to 0.5 (divide the line in half).

**nk1**: Number to be assigned to keypoint generated at division location (defaults to lowest available keypoint number ( [[numstr|NUMSTR]] )).

## Returns

`int`: Keypoint number of the generated keypoint.

## Examples

Create a keypoint on a line from (0, 0, 0) and (10, 0, 0)

``` python
>>> kp0 = (0, 0, 0)
>>> kp1 = (10, 0, 0)
>>> knum0 = mapdl.k("", *kp0)
>>> knum1 = mapdl.k("", *kp1)
>>> lnum = mapdl.l(knum0, knum1)
>>> lnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KL.html
