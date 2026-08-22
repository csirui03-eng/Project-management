---
apdl: "DKDELE"
method: dkdele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_constraints.SolidConstraints.dkdele
generated: 2026-08-22
tags: [mapdl-command]
---

# DKDELE

PyMAPDL: `mapdl.dkdele(kpoi='', lab='', **kwargs)`

Deletes DOF constraints at a keypoint.

## Parameters

**kpoi**: Keypoint for which constraint is to be deleted. If ALL, delete for all selected keypoints ( [[ksel|KSEL]] ). If `KPOI` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `KPOI`.

**lab**: Valid degree of freedom label. If ALL, use all appropriate labels. Structural labels: UX, UY, or UZ (displacements); ROTX, ROTY, or ROTZ (rotations); WARP (warping). Thermal labels: TEMP, TBOT, TE2, TE3,..., TTOP (temperature). Acoustic labels: PRES (pressure); UX, UY, or UZ (displacements for FSI coupled elements). Electric label: VOLT (voltage). Magnetic labels: MAG (scalar magnetic potential); AZ (vector magnetic potential). Diffusion label: CONC (concentration).

## Notes

Deletes the degree of freedom constraints (and all corresponding finite element constraints) at a keypoint. See the [[ddele|DDELE]] command for details.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DKDELE.html
