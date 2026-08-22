---
apdl: "NSUBST"
method: nsubst
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.nsubst
generated: 2026-08-22
tags: [mapdl-command]
---

# NSUBST

PyMAPDL: `mapdl.nsubst(nsbstp='', nsbmx='', nsbmn='', carry='', **kwargs)`

Specifies the number of substeps to be taken this load step.

## Parameters

**nsbstp**

Number of substeps to be used for this load step (that is, the time step size or frequency increment). If automatic time stepping is used ( [[autots|AUTOTS]] ), `NSBSTP` defines the size of the first substep.

If contact elements ( `TARGE169`, `TARGE170`, `CONTA172`, `CONTA174`, `CONTA175`, or `CONTA177` ) are used, defaults to 1 or 20 substeps, depending on the physics of the model. If none of these contact elements are used, defaults to 1 substep.

**nsbmx**: Maximum number of substeps to be taken (that is, the minimum time step size) if automatic time stepping is used. The program automatically determines the default based on the physics of the model.

**nsbmn**: Minimum number of substeps to be taken (that is, the maximum time step size) if automatic time stepping is used. The program automatically determines the default based on the physics of the model.

**carry**

Time step carryover key (program-determined default depending on the problem physics):

- `OFF` - Use `NSBSTP` to define time step at start of each load step.
- `ON` - Use final time step from previous load step as the starting time step (if automatic time stepping is used).

The program automatically determines the default based on the physics of the model.

## Notes

See [[deltim|DELTIM]] for an alternative input. It is recommended that all fields of this command be specified for solution efficiency and robustness.

When the arc-length method is active ( [[arclen|ARCLEN]] command), the `NSBMX` and `NSBMN` arguments are ignored.

Changing the number of substeps upon restarting an analysis during a load step is not recommended. You should only change the number of substeps between load steps.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NSUBST.html
