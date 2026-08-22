---
apdl: "USRCAL"
method: usrcal
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.usrcal
generated: 2026-08-22
tags: [mapdl-command]
---

# USRCAL

PyMAPDL: `mapdl.usrcal(rnam1='', rnam2='', rnam3='', rnam4='', rnam5='', rnam6='', rnam7='', rnam8='', rnam9='', **kwargs)`

Allows user-solution subroutines to be activated or deactivated.

## Parameters

**rnam1**, **rnam2**, **rnam3**, **rnam4**, **rnam5**, **rnam6**, **rnam7**, **rnam8**, **rnam9**

User-defined solution subroutine names to be activated. Up to nine may be defined on one command or multiple commands may be used. If `Rnam1` = ALL, activate all valid user subroutines. If `Rnam1` = NONE, deactivate all valid user subroutines. All characters are required:

- `USREFL` - Allows user defined scalar field (body force) loads.
- `USERCV` - Allows user defined convection (surface) loads.
- `USERPR` - Allows user defined pressure (surface) loads.
- `USERFX` - Allows user-defined heat flux (surface) loads.
- `USERCH` - Allows user-defined charge density (surface) loads.
- `USERFD` - Computes the complex load vector for the frequency domain logic.
- `USEROU` - Allows user supplied element output.
- `USOLBEG` - Allows user access before each solution.
- `ULDBEG` - Allows user access before each load step.
- `USSBEG` - Allows user access before each substep.
- `UITBEG` - Allows user access before each equilibrium iteration.
- `UITFIN` - Allows user access after each equilibrium iteration.
- `USSFIN` - Allows user access after each substep.
- `ULDFIN` - Allows user access after each load step.
- `USOLFIN` - Allows user access after each solution.
- `UANFIN` - Allows user access at end of run.
- `UELMATX` - Allows user access to element matrices and load vectors.
- `UTIMEINC` - Allows a user-defined time step, overriding the program-determined time step.
- `UCNVRG` - Allows user-defined convergence checking, overriding the program-determined convergence.

## Notes

Allows certain user-solution subroutines to be activated or deactivated (system-dependent). This command only affects the subroutines named. Other user subroutines (such as user elements, user creep, etc.) have their own activation controls described with the feature.

The UAnBeg subroutine that allows user access at the start of a run does not require activation by this command; it is automatically activated when the program is started.

The routines are commented and should be listed after performing a custom installation from the distribution media for more details. See also the [Advanced Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advoceanloading.html) for a general description of user- programmable features.

You must have system permission, system access, and knowledge to write, compile, and link the appropriate subroutines into the program at your site.

All routines should be written in FORTRAN. (For more information about FORTRAN compilers, refer to either the [Ansys, Inc. Windows Installation Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/installation/win_product_table.html) or the [Ansys, Inc. Linux Installation Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/installation/lin_product_table.html) for details specific to your platform or operating system.)

Issue **USRCAL**,STAT to list the status of these user subroutines.

Because a user-programmed subroutine is a nonstandard use of the program, the verification of any Mechanical APDL run incorporating these commands is entirely your responsibility. In any contact with customer support regarding the performance of a custom version of Mechanical APDL, explicitly state that a user-programmable feature has been used.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_USRCAL.html
