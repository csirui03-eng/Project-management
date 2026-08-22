---
apdl: "SEMIIMPLICIT"
method: semiimplicit
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.semiimplicit
generated: 2026-08-22
tags: [mapdl-command]
---

# SEMIIMPLICIT

PyMAPDL: `mapdl.semiimplicit(option='', type_='', value='', **kwargs)`

Specifies parameters for a semi-implicit solution.

## Parameters

**option**

Option to be performed:

- `ETOI` - Criterion for transitioning from the semi-implicit solution phase to the implicit solution phase.
- `MSCA` - Selective mass scaling factor used during the semi-implicit solution phase.
- `SFAC` - Safety factor for time incrementation used during the semi-implicit solution phase.
- `AUTS` - Automatic time stepping and bisection controls used during the semi-implicit solution phase.
- `BVIS` - Bulk viscosity controls used during the semi-implicit solution phase.
- `EFRQ` - Output and restart file frequency used during the semi-implicit solution phase.

**type_**: Additional input; varies depending on the `Option` value. See table below.

**value**: Additional input; varies depending on the `Option` and `Type` values. See table below.

## Notes

This command triggers a [semi-implicit solution scheme](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/semi_limitations.html) in which the analysis transitions to a semi-implicit solution method when the implicit solution method fails to converge. The command is valid only in the solution processor ( [[slashsolu|/SOLU]] ) and must be defined before the first [[solve|SOLVE]] command.

The **SEMIIMPLICIT** command can be used in a restart, even if the base analysis did not include the command. Therefore, a problem that failed in the implicit analysis can be restarted with this command so that it can transition to the semi-implicit method and solve further.

The **SEMIIMPLICIT** command can overwrite the values on some commands, as described in the following table.

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SEMI.html
