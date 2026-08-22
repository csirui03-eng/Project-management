---
apdl: "IRLF"
method: irlf
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.inertia.Inertia.irlf
generated: 2026-08-22
tags: [mapdl-command]
---

# IRLF

PyMAPDL: `mapdl.irlf(key='', printfreq='', rampkey='', **kwargs)`

Specifies that inertia relief calculations are to be performed.

## Parameters

**key**

Calculation key:

- `0` - No inertia relief calculations.
- `1` - Counterbalance loads with inertia relief forces.
- `-1` - Precalculate masses for summary printout only (no inertia relief).

**printfreq**

Frequency at which inertia relief information is printed during substeps in a nonlinear static or eigenvalue buckling analysis. This value must be a positive integer, 0, or ALL, as described below.

- `0` - No inertia relief information is printed during the Newton Raphson substeps (default).
- `n` - Prints inertia relief information every `n` th substep of each load step.
- `ALL` - Prints inertia relief information every substep.

**rampkey**

Key to control ramping of rigid body accelerations. See notes for steps to achieve convergence when turning on the inertia relief option in the second or later load step of a nonlinear analysis.

- `0` - (Default) Rigid body acceleration is stepped and ramped together with total external loads following specifications set using the [[kbc|KBC]] command. Normally, the inertia relief option is turned on at the first load step.
- `1` - Ramp the rigid body accelerations alone following specifications set by the [[kbc|KBC]] command. This option is only used for better convergence when the inertia relief load step is nonlinear and the inertia relief option is turned on from a later load step (other than the first). It works with [[kbc|KBC]],0 specified and no new loads added to the current load step. After the current load step, `RampKey` is automatically set to 0. See .

## Notes

The **IRLF** command specifies that the program is to calculate accelerations to counterbalance the applied loads (inertia relief). Displacement constraints on the structure should be only those necessary to prevent rigid-body motions (3 are needed for a 2D structure and 6 for a 3D structure). If the minimum number of displacement constraints are applied and it is a linear static analysis, the sum of the reaction forces at the constrained points will be zero. However, if it is a nonlinear static analysis ( [[nlgeom|NLGEOM]],ON), the sum of reaction forces at the constrained points will be approximately zero due to the error introduced by nonlinear iterations. Accelerations are calculated from the element mass matrices and the applied forces. Data needed to calculate the mass (such as density) must be input. Both translational and rotational accelerations may be calculated.

This option applies to the following analyses: static (linear or nonlinear), linear perturbation static, and buckling (see [Including Inertia Relief Calculations](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS2_6.html#) [Supported Analysis Types for Inertia Relief](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool2.html#) Elements that operate in the nodal coordinate system and axisymmetric or generalized plane strain elements are not allowed. Symmetry models are not valid for inertia relief analysis. Models with both 2D and 3D element types are not recommended.

Loads may be input as usual. Displacements and stresses are calculated as usual.

An automatic inertia relief capability is available for linear static analysis only. See the [[airl|AIRL]] command for details.

Use [[irlist|IRLIST]] to print inertia relief calculation results. Note that [[irlist|IRLIST]] can only be issued at the end of the analysis, right after the [[solve|SOLVE]] command in the nonlinear case. To print information during substeps in a nonlinear static or eigenvalue buckling analysis, set `PrintFreq` as described above. The mass and moment of inertia summary printed before the solution is accurate (because of the additional pre-calculations required for inertia relief). See [Inertia Relief](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool2.html#thy_InertiaRelAnalysisTypes)

Turning On the Inertia Relief Option in the Second or Later Load Step If the inertia relief option is turned on in the second or later load step in a nonlinear static analysis, follow these precautionary steps for easy nonlinear convergence:

At the second or higher load step, where **IRLF**,1 is issued the first time, do not apply new external loads.

Set `Rampkey` = 1 at this load step and [[kbc|KBC]],0 so that the rigid body accelerations are ramped.

Use the [[nsubst|NSUBST]] or [[deltim|DELTIM]] command to allow more substeps in this load step.

When a superelement ( `MATRIX50` ) is present in the model, any DOF constraints that you need to apply ( [[d|D]] ) on a degree of freedom (DOF) belonging to the superelement must be applied in the [use pass](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/an9Auq1d6ldm.html#advobsl5jla062999) of the `MATRIX50` element ( not in the [generation pass](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/advcmssuperelem.html#usingcms_elemcalc) ). The command has no effect in the [generation pass](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/aKa7uq1a9ldm.html#advsupmtr2jla062999) of a substructure. In the [expansion pass](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/axcAuq367ldm.html#adv5note4jla062999), precalculation of masses for summary printout ( **IRLF**,-1) occurs only on elements that are part of the substructure.

This command is also valid in PREP7.

**Example Usage** Example command inputs for including inertia relief calculations in a static analysis with geometric nonlinearity, a linear perturbation static analysis, and a linear perturbation buckling analysis are found in [Including Inertia Relief Calculations](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS2_6.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_IRLF.html
