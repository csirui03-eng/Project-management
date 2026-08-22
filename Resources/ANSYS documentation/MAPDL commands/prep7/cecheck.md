---
apdl: "CECHECK"
method: cecheck
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.database.Database.cecheck
generated: 2026-08-22
tags: [mapdl-command]
---

# CECHECK

PyMAPDL: `mapdl.cecheck(itemlab='', tolerance='', dof='', **kwargs)`

Check constraint equations and couplings for rigid body motions.

## Parameters

**itemlab**

Item indicating what is to be checked:

- `CE` - Check constraint equations only
- `CP` - Check couplings only
- `ALL` - Check both CE and CP

**tolerance**: Allowed amount of out-of-balance for any constraint equation or coupled set. The default value of 1.0e-6 is usually good.

**dof**: Specifies which DOF is to be checked. Default is RIGID, the usual option. Other choices are individual DOF such as UX, ROTZ, etc. or THERM. The THERM option will check the constraint equations or coupled sets for free thermal expansions, whereas the individual DOFs check under rigid body motions. ALL is RIGID and THERM.

## Notes

This command imposes a rigid body motion on the nodes attached to the constraint equation or coupled set and makes sure that no internal forces are generated for such rigid body motions. Generation of internal forces by rigid body motions usually indicates an error in the equation specification (possibly due to nodal coordinate rotations). The THERM option does a similar check to see that no internal forces are created by the equations if the body does a free thermal expansion (this check assumes a single isotropic coefficient of expansion).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CECHECK.html
