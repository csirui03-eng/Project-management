---
apdl: "/UCMD"
method: ucmd
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.abbreviations.Abbreviations.ucmd
generated: 2026-08-22
tags: [mapdl-command]
---

# /UCMD

PyMAPDL: `mapdl.ucmd(cmd='', srnum='', **kwargs)`

Assigns a user-defined command name.

## Parameters

**cmd**: User-defined command name. Only the first four characters are significant. Must not conflict with any Mechanical APDL command name or any user unknown-command macro name.

**srnum**: User subroutine number (1 to 10) programmed for this command. For example, the command **/UCMD**,MYCMD,3 will execute subroutine USER03 whenever the command **MYCMD** is entered. Use a blank command name to disassociate `SRNUM` from its command. For example, **/UCMD** ,,3 removes **MYCMD** as a command.

## Notes

Assigns a user-defined command name to a user-programmable (system-dependent) subroutine. This feature allows user-defined commands to be programmed into Mechanical APDL. Once programmed, this command can be input to the program like other commands, and can also be included in the Mechanical APDL start-up file.

Up to 10 subroutines are available for user-defined commands (USER01 to USER10). You must have system permission, system access, and knowledge to write, compile, and link the appropriate subprocessors into Mechanical APDL at your site.

All routines should be written in FORTRAN. For more information about FORTRAN compilers, refer to either the [Ansys, Inc. Windows Installation Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/installation/win_product_table.html) or the [Ansys, Inc. Linux Installation Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/installation/lin_product_table.html) for details specific to your platform or operating system.

The USER01 routine is commented and should be listed from the distribution media (system dependent) for more details.

Issue **/UCMD**,STAT to list all user-defined command names.

Because a user-programmed command is a nonstandard use of the program, the verification of any Mechanical APDL run incorporating these commands is your responsibility. In any contact with Mechanical APDL customer support regarding the performance of a custom version of Mechanical APDL, explicitly state that a user-programmable feature has been used.

See [User-Programmable Features (UPFs)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_ADV7_1.html#aRzouq21ldm) [Guide to User-Programmable Features](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_prog/ansysprog_aero_fullycoupled.html)

See [[ulib|*ULIB]] for another way of defining user commands.

This command is valid only at the Begin Level.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_UCMD.html
