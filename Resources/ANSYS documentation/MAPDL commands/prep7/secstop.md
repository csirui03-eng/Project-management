---
apdl: "SECSTOP"
method: secstop
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.secstop
generated: 2026-08-22
tags: [mapdl-command]
---

# SECSTOP

PyMAPDL: `mapdl.secstop(dof0='', minvalue0='', maxvalue0='', dof1='', minvalue1='', maxvalue1='', dof2='', minvalue2='', maxvalue2='', addional_command_arg='', **kwargs)`

Specifies stops on the components of relative motion in a joint element.

## Parameters

**dof0**, **minvalue0**, **maxvalue0**, **dof1**, **minvalue1**, **maxvalue1**, **dof2**, **minvalue2**, **maxvalue2**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SECSTOP.html) for further information.

**addional_command_arg**: Additional arguments can be passed to the initial command. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SECSTOP.html) for further information.

## Notes

Stops restrict motion in a DOF; motion beyond the MINVALUE or MAXVALUE is prevented (motion away from a limit is allowed). You can specify up to three stops. If necessary, you can repeat the command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SECSTOP.html
