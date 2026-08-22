---
apdl: "KPLOT"
method: kplot
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.kplot
generated: 2026-08-22
tags: [mapdl-command]
---

# KPLOT

PyMAPDL: `mapdl.kplot(np1='', np2='', ninc='', lab='', **kwargs)`

Displays the selected keypoints.

## Parameters

**np1**, **np2**, **ninc**: Display keypoints from `NP1` to `NP2` (defaults to `NP1` ) in steps of `NINC` (defaults to 1). If `NP1` = ALL (default), `NP2` and `NINC` are ignored and all selected keypoints ( [[ksel|KSEL]] ) are displayed.

**lab**

Determines what keypoints are plotted (one of the following):

- `(blank)` - Plots all keypoints.
- `HPT` - Plots only those keypoints that are hard points.

## Notes

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KPLOT.html
