---
apdl: "*USE"
method: use
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.macro_files.MacroFiles.use
generated: 2026-08-22
tags: [mapdl-command]
---

# *USE

PyMAPDL: `mapdl.use(name='', arg1='', arg2='', arg3='', arg4='', arg5='', arg6='', arg7='', arg8='', arg9='', ar10='', ar11='', ar12='', ar13='', ar14='', ag15='', ar16='', ar17='', ar18='', **kwargs)`

Executes a macro file.

## Parameters

**name**: Name (32 characters maximum, beginning with a letter) identifying the macro file or a macro block on a macro library file.

**arg1**, **arg2**, **arg3**, **arg4**, **arg5**, **arg6**, **arg7**, **arg8**, **arg9**: Values passed into the file or block where the parameters ARG1 through ARG9 and AR10 through AR18 are referenced. Values may be numbers, alphanumeric character strings (up to 32 characters enclosed in single quotes), parameters (numeric or character) or parametric expressions. See below for additional details.

**ar10**, **ar11**, **ar12**, **ar13**, **ar14**, **ag15**, **ar16**, **ar17**, **ar18**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_USE.html) for further information.

## Notes

Causes execution of a macro file called `Name`, or, if not found, a macro block " `Name` " on the macro library file ( [[ulib|*ULIB]] ). Argument values (numeric or character) are passed into the file or block and substituted for local parameters ARG1, ARG2,..., AR18. The file `Name` may also be executed as an "unknown command" (that is, without the **\*USE** command name) as described below.

A macro is a sequence of Mechanical APDL commands (as many as needed) recorded in a file or in a macro block in a library file (specified with the [[ulib|*ULIB]] command). The file or block is typically executed via **\*USE**. In addition to command, numerical and alphanumeric data, the macro can include parameters which will be assigned numerical or alphanumerical character values when the macro is used. Use of the macro can be repeated (within a do-loop, for example) with the parameters incremented.

A macro is defined within a run by enclosing a sequence of data input commands between [[create|*CREATE]] and [[end|*END]] commands. The data input commands are passive (not executed) while being written to the macro file. The macro file (without [[create|*CREATE]] and [[end|*END]] ) can also be created external to Mechanical APDL.

Up to 99 specially named scalar parameters, ARG1 to AR99, are locally available to each macro:

- The prefix for the first nine parameters is ARG, and the prefix for the remaining 90 parameters is AR.
- A local parameter is not affected by, nor does it affect, other parameters, even those of the same name, which are used outside of the macro. The only way a local parameter can affect, or be affected by, parameters outside the macro is if values are passed out of, or into, the macro by an argument list.
- Parameters ARG1 through AR18 can have their values (numeric or character) passed via the argument list on **\*USE**. (ARG1 through AR19 can be passed as arguments on the unknown-command macro.) Parameters AR19 through AR99 (AR20 through AR99 in the unknown-command macro) are available solely for use within the macro; they cannot be passed via an argument list.
- Local parameters are available to do-loops and to [[input|/INPUT]] files processed within the macro. In addition to an ARG1-AR99 set for each macro, another ARG1-AR99 set is available external to all macros, local to "non-macro" space.

A macro is exited after its last line is executed. Macros may be nested (such as a **\*USE** or an unknown command within a macro). Each nested macro has its own set of 99 local parameters. Only one set of local parameters can be active at a time and that is the set corresponding to the macro currently being executed or to the set external to all macros (if any). When a nested macro completes execution, the previous set of local parameters once again becomes available. Issue [[starstatus|*STATUS]],ARGX to view current macro parameter values.

An alternate way of executing a macro file is via the unknown-command route. If a command unknown to Mechanical APDL is entered, a search for a file of that name (plus a `.MAC` suffix) is made. If the file exists, it is executed, if not, the "unknown command" message is output. Thus, you can write your own commands in terms of other Mechanical APDL commands. The procedure is similar to issuing **\*USE** with the unknown command in the `Name` field. For example, the command **CMD** ,10,20,30 is internally similar to **\*USE**,CMD,10,20,30. The macro file named `CMD.MAC` is executed with the three parameters. The **\*USE** macro description also applies to the unknown- command macro, except that various directories are searched and a suffix ( `.MAC` ) is assumed. Also, a macro library file is not searched.

A three-level directory search for the unknown-command macro file may be available. The search order may be: 1) a high-level system directory, 2) the log-in directory, and 3) the local (working) directory. Issue [[psearch|/PSEARCH]] to change the directory search path. For an unknown command **CMD**, the first file named `CMD.MAC` found to exist in the search order is executed. The command can be input in lower-, upper-, or mixed-case; however, it converts to uppercase automatically before the file name search occurs. On systems that preserve the case as it was input, a file matching the upper-case name is used first, followed by a file with the matching the lower-case name, and finally a file matching the mixed-case name. All macro files placed in the `apdl` directory must be upper-case.

Because undocumented commands exist in Mechanical APDL, you should issue the command intended for the macro file name to ensure that the unknown-command message is output in the processor where it is to be used. If the macro is to be used in other processors, the other processors must also be checked.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_USE.html
