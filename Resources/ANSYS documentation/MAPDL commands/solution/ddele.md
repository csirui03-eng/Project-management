---
apdl: "DDELE"
method: ddele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_constraints.FeConstraints.ddele
generated: 2026-08-22
tags: [mapdl-command]
---

# DDELE

PyMAPDL: `mapdl.ddele(node='', lab='', nend='', ninc='', rkey='', **kwargs)`

Deletes degree-of-freedom constraints.

## Parameters

**node**: Node for which constraint is to be deleted. If ALL, `NEND` and `NINC` are ignored and constraints for all selected nodes ( [[nsel|NSEL]] ) are deleted. If `NODE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE`.

**lab**

Valid degree of freedom label. If ALL, use all selected labels ( [[dofsel|DOFSEL]] ). Structural labels: UX, UY, or UZ (displacements); ROTX, ROTY, or ROTZ (rotations); WARP (warping). Thermal labels: TEMP, TBOT, TE2, TE3,..., TTOP (temperature). Acoustic labels: PRES (pressure); UX, UY, or UZ (displacements for FSI coupled elements). Electric label: VOLT (voltage). Magnetic labels: MAG (scalar magnetic potential); AZ (vector magnetic potential). Diffusion label: CONC (concentration).

In structural analyses, the following velocity and acceleration load labels are also valid: VELX, VELY, VELZ (translational velocities); OMGX, OMGY, OMGZ (rotational velocities); ACCX, ACCY, ACCZ (translational accelerations); DMGX, DMGY, DMGZ (rotational accelerations).

In structural analyses, HDSP (hydrostatic pressure) is also valid.

If the node is connected to an `ELBOW290` element, the following pipe cross-section degree of freedom labels are also valid: SE, SO, SW, SRA, and SRT. (For details, see the `ELBOW290` documentation.) The degrees of freedom are not included when `Lab` = ALL. To constrain all cross- section degrees of freedom, specify `Lab` = SECT.

**nend**, **ninc**: Delete constraints from `NODE` to `NEND` (defaults to `NODE` ) in steps of `NINC` (defaults to 1).

**rkey**

Ramping option:

- `OFF` - Loads are step-removed (default).

- `ON or FORCE` - Forces on the specified degrees of freedom ( `Lab` ) are ramped during the next load step. The forces are ramped from the reaction forces of the previous load step, regardless of whether or not a constraint was present. If the specified node(s) and degree(s) of freedom has a force value currently defined, the force is ramped from the reaction force value to the currently applied force value. If no force is currently applied, the force is ramped from the reaction force value to zero. The ramping behavior is not in effect if the subsequent force is applied in tabular format.

  For degrees of freedom other than structural and TEMP, UX, UY, YZ, ROTX, ROTY, and ROTZ

  > when performing a restart at an intermediate point during a load step, Not at the beginning or end

  of a load step.

  > the reaction-force data is not available. Therefore, the force is ramped from zero to the currently

  applied force value (if it exists) for the specified node(s) and degree(s) of freedom.

  For structural and TEMP degrees of freedom, during a restart from an intermediate point during a load step, the reaction-force data is available. Therefore, it is ramped down during this restart step if no other loads are applied. See [[ddele#Notes|DDELE]] for more information about the behavior of this option.

## Notes

Deleting a constraint is not the same as setting it to zero (which fixes the degree of freedom to a zero value). Deleting a constraint has the same effect as deactivating, releasing, or setting the constraint free. The node and the degree of freedom label must be selected ( [[nsel|NSEL]], [[dofsel|DOFSEL]] ).

For structural degrees of freedom, the following limitation exists when the analysis is restarted:

- If a new force is applied ( [[f|F]] ) upon restart of the load step during which **DDELE**, `NODE`, `DofLabel`,,,RFORCE (or ON) was issued, the force will show a jump to the current value at the time of restart before being ramped to its final value.

Upon restart, it is good practice is to allow the reaction force to ramp down to zero in a load step, then to apply new loads in the next load step.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DDELE.html
