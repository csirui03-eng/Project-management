---
apdl: "KMODIF"
method: kmodif
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.kmodif
generated: 2026-08-22
tags: [mapdl-command]
---

# KMODIF

PyMAPDL: `mapdl.kmodif(npt='', x='', y='', z='', **kwargs)`

Modifies an existing keypoint.

## Parameters

**npt**: Modify coordinates of this keypoint. If `NPT` = ALL, modify coordinates of all selected keypoints ( [[ksel|KSEL]] ). If `NPT` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NPT`.

**x**, **y**, **z**: Replace the previous coordinate values assigned to this keypoint with these corresponding coordinate values. Values are interpreted according to the active coordinate system (R, θ, Z for cylindrical, R, θ,Φ for spherical). If `X` = P, graphical picking is used to locate keypoint and `Y` and `Z` are ignored. A blank retains the previous value. You cannot specify `Y` = P.

## Notes

Lines, areas, and volumes attached to the modified keypoint (if any) must all be selected and will be redefined using the active coordinate system. However, solid modeling in a toroidal coordinate system is not recommended.

> [!WARNING]
> Redefined entities may be removed from any defined components and assemblies. Nodes and elements will be automatically cleared from any redefined keypoints, lines, areas, or volumes.

The **KMODIF** command moves keypoints for geometry modification without validating underlying entities. To merge keypoints and update higher order entities, issue the [[nummrg|NUMMRG]] command instead.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KMODIF.html
