---
apdl: "AIRL"
method: airl
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.inertia.Inertia.airl
generated: 2026-08-22
tags: [mapdl-command]
---

# AIRL

PyMAPDL: `mapdl.airl(nrb='', rigid_calc='', **kwargs)`

Specifies that automatic inertia relief calculations are to be performed.

## Parameters

**nrb**

Number of rigid body modes in the model:

- `AUTO` - Activate automatic inertia relief (default). The program automatically determines the number of rigid body modes.
- `n` - Activate automatic inertia relief with the assumption of `n` rigid body modes (1≤ `n` ≤ 6).
- `0` - Deactivate automatic inertia relief.

**rigid_calc**

Method for computing the rigid body modes:

- `0` - Use an eigensolver to compute rigid body modes (default).
- `1` - Use the geometry to compute rigid body modes (valid only when `NRB` = AUTO). The geometric rigid body vectors are calculated according to in [Participation Factors and Mode Coefficients](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc7.html#eqe483f2f2-aaa1-4080-a835-10c0e1e18f57)

## Notes

The **AIRL** command activates automatic inertia relief for models having up to six rigid body modes. This method is only valid for linear static analyses ( [[antype|ANTYPE]],STATIC).

By default ( `NRB` = AUTO), the number of rigid body modes in the structure is automatically determined. The static solution is altered so that the inertial effects factor into counterbalancing the external loads. This method relies on calculation of the rigid body modes using either an eigensolver ( `RIGID_CALC` = 0, which is the default) or the model geometry ( `RIGID_CALC` = 1).

For the `NRB` = AUTO option, no supports should be defined.

For a model that is partially constrained by design, you must set `NRB` to the number of rigid body modes present in the structure and set `RIGID_CALC` = 0. The use of geometry ( `RIGID_CALC` = 1) to compute the rigid-body modes of a partially constrained model is not supported.

Loads may be input as usual. Displacements and stresses are calculated as usual.

Use [[irlist|IRLIST]] to print inertia relief calculation results. The mass and moment of inertia summary printed before the solution is accurate (because of the additional pre-calculations required for inertia relief). See [Inertia Relief](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool2.html#thy_InertiaRelAnalysisTypes) [Including Inertia Relief Calculations](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS2_6.html#)

This command is also valid in PREP7.

**Example Usage** Example command input for including automatic inertia relief calculations in a linear static analysis is found in [Including Inertia Relief Calculations](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS2_6.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AIRL.html
