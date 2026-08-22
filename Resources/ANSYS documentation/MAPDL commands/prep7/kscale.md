---
apdl: "KSCALE"
method: kscale
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.kscale
generated: 2026-08-22
tags: [mapdl-command]
---

# KSCALE

PyMAPDL: `mapdl.kscale(kinc='', np1='', np2='', ninc='', rx='', ry='', rz='', **kwargs)`

Generates a scaled pattern of keypoints from a given keypoint pattern.

## Parameters

**kinc**: Do this scaling operation one time, incrementing all keypoints in the given pattern by `KINC`. If `KINC` = 0, keypoints will be redefined at the scaled locations.

**np1**, **np2**, **ninc**: Scale keypoints from pattern beginning with `NP1` to `NP2` (defaults to `NP1` ) in steps of `NINC` (defaults to 1). If `NP1` = ALL, `NP2` and `NINC` are ignored and pattern is all selected keypoints ( [[ksel|KSEL]] ). If `NP1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NP1` ( `NP2` and `NINC` are ignored).

**rx**, **ry**, **rz**: Scale factor ratios. Scaling is relative to the origin of the active coordinate system (RR, Rθ, RZ for cylindrical, RR, Rθ, RΦ for spherical). If \> 1.0, pattern is enlarged. If \< 1.0, pattern is reduced. Ratios each default to 1.0.

## Notes

Generates a scaled pattern of keypoints from a given keypoint pattern. Scaling is done in the active coordinate system (see analogous node scaling ( [[nscale|NSCALE]] )). Solid modeling in a toroidal coordinate system is not recommended.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KSCALE.html
