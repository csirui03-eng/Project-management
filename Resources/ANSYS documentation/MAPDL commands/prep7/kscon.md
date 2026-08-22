---
apdl: "KSCON"
method: kscon
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.kscon
generated: 2026-08-22
tags: [mapdl-command]
---

# KSCON

PyMAPDL: `mapdl.kscon(npt='', delr='', kctip='', nthet='', rrat='', **kwargs)`

Specifies a keypoint about which an area mesh will be skewed.

## Parameters

**npt**: Keypoint number at concentration. If `NPT` = ALL, use all selected keypoints. If remaining fields are blank, remove concentration from this keypoint (if unmeshed). If `NPT` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NPT`.

**delr**: Radius of first row of elements about keypoint.

**kctip**

Crack tip singularity key:

- `0` - Do not skew midside nodes, if any, within the element.
- `1` - Skew midside nodes of the first row of elements to the 1/4 point for crack tip singularity.

**nthet**: Number of elements in circumferential direction (defaults to approximately one per 45° (or one per 30°, if `KCTIP` = 1)).

**rrat**: Ratio of 2nd row element size to `DELR` (defaults to 0.75, or 0.5 if `KCTIP` = 1).

## Notes

Defines a concentration keypoint about which an area mesh will be skewed. Useful for modeling stress concentrations and crack tips. During meshing, elements are initially generated circumferentially about, and radially away, from the keypoint. Lines attached to the keypoint are given appropriate divisions and spacing ratios. Only one concentration keypoint per unmeshed area is allowed. Use **KSCON**,STAT to list current status of concentration keypoints. The **KSCON** command does not support 3D modeling.

This command is also valid for [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KSCON.html
