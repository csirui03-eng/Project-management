---
apdl: "*VWRITE"
method: vwrite
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.vwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# *VWRITE

PyMAPDL: `mapdl.vwrite(par1='', par2='', par3='', par4='', par5='', par6='', par7='', par8='', par9='', par10='', par11='', par12='', par13='', par14='', par15='', par16='', par17='', par18='', par19='', **kwargs)`

Writes data to a file in a formatted sequence.

> [!WARNING]
> This command must be run using `non_interactive <ansys.mapdl.core.Mapdl.non_interactive>`. Please visit [Unsupported Interactive Commands](https://mapdl.docs.pyansys.com/version/stable/user_guide/mapdl.html#unsupported-interactive-commands) for further information.

## Parameters

**par1**, **par2**, **par3**, **par4**, **par5**, **par6**, **par7**, **par8**, **par9**, **par10**, **par11**, **par12**, **par13**, **par14**, **par15**, **par16**, **par17**, **par18**, **par19**: You can write up to 19 parameters (or constants) at a time. Any Par values after a blank Par value are ignored. If you leave them all blank, one line will be written (to write a title or a blank line). If you input the keyword SEQU, a sequence of numbers (starting from 1) will be written for that item.

## Notes

### Argument descriptions

- `par1, par2, par3,..., par19 : str` - You can write up to 19 parameters (or constants) at a time. Any Par values after a blank Par value are ignored. If you leave them all blank, one line will be written (to write a title or a blank line). If you input the keyword SEQU, a sequence of numbers (starting from 1) will be written for that item.

You use **\*VWRITE** to write data to a file in a formatted sequence. Data items ( `Par1`, `Par2`, etc.) may be array parameters, scalar parameters, character parameters (scalar or array), or constants. You must evaluate expressions and functions in the data item fields before using the **\*VWRITE** command, since initially they will be evaluated to a constant and remain constant throughout the operation. Unless a file is defined with the [[cfopen|*CFOPEN]] command, data is written to the standard output file. Data written to the standard output file may be diverted to a different file by first switching the current output file with the [[output|/OUTPUT]] command. You can also use the [[mwrite|*MWRITE]] command to write data to a specified file. Both commands contain format descriptors on the line immediately following the command. The format descriptors can be in either FORTRAN or C format.

You must enclose FORTRAN format descriptors in parentheses. They must immediately follow the **\*VWRITE** command on a separate line of the same input file. Do not include the word FORMAT. The format must specify the number of fields to be written per line, the field width, the placement of the decimal point, etc. You should use one field descriptor for each data item written. The write operation uses your system's available FORTRAN FORMAT conventions (see your system FORTRAN manual). You can use any standard FORTRAN real format (such as (4F6.0), (E10.3,2X,D8.2), etc.) and alphanumeric format (A). Alphanumeric strings are limited to a maximum of 8 characters for any field (A8) using the FORTRAN format. Use the "C" format for string arrays larger than 8 characters. Integer (I) and list-directed (2) descriptors may not be used. You can include text in the format as a quoted string. The parentheses must be included in the format and the format must not exceed 80 characters (including parentheses). The output line length is limited to 128 characters.

The "C" format descriptors are used if the first character of the format descriptor line is not a left parenthesis. "C" format descriptors are up to 80 characters long, consisting of text strings and predefined "data descriptors" between the strings where numeric or alphanumeric character data will be inserted. The normal descriptors are %I for integer data, %G for double precision data, %C for alphanumeric character data, and %/ for a line break. There must be one data descriptor for each specified value (8 maximum) in the order of the specified values. The enhanced formats described in [[msg|*MSG]] may also be used.

For array parameter items, you must define the starting array element number. Looping continues (incrementing the vector index number of each array parameter by one) each time you output a line, until the maximum array vector element is written. For example, **\*VWRITE**,A(1) followed by (F6.0) will write one value per output line, that is, A(1), A(2), A(3), A(4), etc. You write constants and scalar parameters with the same values for each loop. You can also control the number of loops and loop skipping with the [[vlen|*VLEN]] and [[vmask|*VMASK]] commands. The vector specifications [[vabs|*VABS]], [[vfact|*VFACT]], and [[vcum|*VCUM]] do not apply to this command. If looping continues beyond the supplied data array's length, zeros will be output for numeric array parameters and blanks for character array parameters. For multi-dimensioned array parameters, only the first (row) subscript is incremented. See the [[voper|*VOPER]] command for details. If you are in the GUI, the **\*VWRITE** command must be contained in an externally prepared file and read into Mechanical APDL (that is, [[use|*USE]], [[input|/INPUT]], etc.).

If `Par` is a table array name, the subscripts refer to the index numbers of the table and not the index values of its primary variables. See [[starset|*SET]] if you want to evaluate a table array at certain values of its primary variables for writing.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VWRITE.html
