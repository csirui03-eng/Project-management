---
apdl: "IC"
method: ic
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.ic
generated: 2026-08-22
tags: [mapdl-command]
---

# IC

PyMAPDL: `mapdl.ic(node='', lab='', value='', value2='', nend='', ninc='', **kwargs)`

Specifies initial conditions at nodes.

## Parameters

**node**: Node at which initial condition is to be specified. If ALL, apply to all selected nodes ( [[nsel|NSEL]] ). If `NODE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may be substituted for `NODE`.

**lab**

Degree-of-freedom label for which the initial condition is to be specified. If ALL, use all appropriate labels.

- **Structural labels** : UX, UY, or UZ (displacements); ROTX, ROTY, or ROTZ (rotations); HDSP (hydrostatic pressure); PRES (pore pressure)
- For structural static and transient analyses, specify translational and rotational velocities as initial conditions using these labels: VELX, VELY, VELZ (translational velocities); OMGX, OMGY, OMGZ (rotational velocities).
- For structural transient analysis, specify translational and rotational accelerations as initial conditions using these labels: ACCX, ACCY, ACCZ (translational accelerations); DMGX, DMGY, DMGZ (rotational accelerations).
- The velocity and acceleration initial conditions are not included with `Lab` = ALL.
- **Thermal labels** : TEMP, TBOT, TE2, TE3,..., TTOP (temperature)
- **Magnetic labels** : MAG (scalar magnetic potential); AZ (vector magnetic potential)
- **Diffusion label** : CONC (concentration)
- **Acoustic label** : ENKE (acoustic energy density)

**value**: Initial value of the degree of freedom. Defaults to the program default for that degree of freedom (0.0 for structural analysis, [[tunif|TUNIF]] for thermal analysis, etc.). Values are in the nodal coordinate system and in radians for rotational degrees of freedom.

**value2**: Second-order degree of freedom value, mainly used for non-structural DOF where VELX can't be used. Defaults to the program default for that degree of freedom (0.0 for structural analysis). Values are in the nodal coordinate system and in radians/time for rotational degrees of freedom.

**nend**, **ninc**: Specifies the same initial condition values at the range of nodes from `NODE` to `NEND` (defaults to `NODE` ), in steps of `NINC` (defaults to 1).

## Notes

The **IC** command specifies initial conditions, which are the initial values of the specified degrees of freedom. It is valid only for a static analysis and full method transient analysis ( [[timint|TIMINT]],ON and [[trnopt|TRNOPT]],FULL). For the transient, the initial value is specified at the beginning of the first load step, that is, at time = 0.0.

If constraints ( [[d|D]], [[dsym|DSYM]], etc.) and initial conditions are applied at the same node, the constraint specification overrides. Exercise caution when specifying constraints. The degree-of- freedom values start from zero, or the first value given in the table when table name is specified. To match the nonzero initial condition value with the initial value for degree-of-freedom constraint, use a table for the degree-of-freedom constraint.

For thermal analyses, any [[tunif|TUNIF]] specification should be applied before the **IC** command; otherwise, the [[tunif|TUNIF]] specification is ignored. If the **IC** command is input before any [[tunif|TUNIF]] specification, use the [[icdele|ICDELE]] command and then reissue any [[tunif|TUNIF]] specification and then follow with the **IC** command.

When issuing the **IC** command for elements `SOLID278` [Layered Thermal Solid](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_SOLID278.html#SOLID278L.fig.1) and `SOLID279` [Layered Thermal Solid](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_SOLID279.html#SOLID279L.fig.1) with through-the-thickness degrees of freedom (KEYOPT(3) = 2), layers are always interpolated linearly based on the location of the degrees of freedom.

Define consistent initial conditions. For example, if you define an initial velocity at a single degree of freedom, the initial velocity at every other degree of freedom will be 0.0, potentially leading to conflicting initial conditions. In most cases, you should define initial conditions at every unconstrained degree of freedom in your model. If you define an initial condition for any degree of freedom at the pilot node of a rigid body (see [Modeling Rigid Bodies](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctecrigidbodies.html#strmodrigidbod) in the [Contact Technology Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_flpressexamp.html) for the definition of rigid body), then the same initial condition must also be defined for the same degree of freedom on all other nodes of the rigid body.

After a solution has been performed, the specified initial conditions are overwritten by the actual solution and are no longer available. You must respecify them if you want to perform a subsequent analysis. You may want to keep a database file saved prior to the first solution for subsequent reuse.

If you use the [[cdwrite|CDWRITE]] command to archive your model, initial displacements, temperatures, etc. specified via the **IC** command are not written to the archive file; initial velocities and accelerations are written.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_IC.html
