---
apdl: "*SET"
method: starset
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.starset
generated: 2026-08-22
tags: [mapdl-command]
---

# *SET

PyMAPDL: `mapdl.starset(par='', value='', val2='', val3='', val4='', val5='', val6='', val7='', val8='', val9='', val10='', **kwargs)`

Assigns values to user-named parameters.

## Parameters

**par**

An alphanumeric name used to identify this parameter. `Par` can contain up to 32 characters, beginning with a letter and containing only letters, numbers, and underscores. Examples:

``` apdl
ABC A3X TOP_END
```

Command names, function names, label names, component and assembly names, etc., are invalid, as are parameter names beginning with an underscore (for example,

``` apdl
_LOOP
```

).

Parameter names ending in an underscore are not listed by the [[starstatus|*STATUS]] command. Array parameter names must be followed by a subscript, and the entire expression must be 32 characters or less. Examples:

``` apdl
A(1,1) NEW_VAL(3,2,5) RESULT(1000)
```

There is no character parameter substitution for the `Par` field. Table parameters used in command fields (where constant values are normally given) are limited to 32 characters.

**value**

Numerical value or alphanumeric character string (up to 32 characters enclosed in single quotes) to be assigned to this parameter. Examples:

``` apdl
A(1,3)=7.4 B='ABC3'
```

Can also be a parameter or a parametric expression. Examples:

``` apdl
C=A(1,3) A(2,2)=(C+4)/2
```

``` apdl
C=A(1,3) A(2,2)=(C+4)/2

If ``VALUE`` is the table array name, the subscripts are the values of the primary variables
```

and the table is evaluated at these specified index values.

If blank, delete this parameter. Example:

``` apdl
A=
```

deletes parameter

``` apdl
A
```

``` apdl
A
```

**val2**, **val3**, **val4**, **val5**, **val6**, **val7**, **val8**, **val9**, **val10**

If `Par` is an array parameter, values `VAL2` through `VAL10` (up to the last nonblank value) are sequentially assigned to the succeeding array elements of the column. Examples:

``` apdl
*SET,A(1,4),10,11
```

assigns

``` apdl
A(1,4)=10, A(2,4)=11
```

``` apdl
A(1,4)=10, A(2,4)=11
```

``` apdl
*SET,B(2,3),'file10','file11'
```

assigns

``` apdl
B(2,3)='file10',           B(3,3)='file11'
```

``` apdl
B(2,3)='file10',           B(3,3)='file11'
```

## Notes

### Argument descriptions

- `par : str` - An alphanumeric name used to identify this parameter. `Par` can contain up to 32 characters, beginning with a letter and containing only letters, numbers, and underscores. Examples:

  ``` apdl
  ABC A3X TOP_END
  ```

  Command names, function names, label names, component and assembly names, etc., are invalid, as are parameter names beginning with an underscore (for example,

  ``` apdl
  _LOOP
  ```

  ).

  Parameter names ending in an underscore are not listed by the [[starstatus|*STATUS]] command. Array parameter names must be followed by a subscript, and the entire expression must be 32 characters or less. Examples:

  ``` apdl
  A(1,1) NEW_VAL(3,2,5) RESULT(1000)
  ```

  There is no character parameter substitution for the `Par` field. Table parameters used in command fields (where constant values are normally given) are limited to 32 characters.

- `value : str` - Numerical value or alphanumeric character string (up to 32 characters enclosed in single quotes) to be assigned to this parameter. Examples:

  ``` apdl
  A(1,3)=7.4 B='ABC3'
  ```

  Can also be a parameter or a parametric expression. Examples:

  ``` apdl
  C=A(1,3) A(2,2)=(C+4)/2
  ```

  ``` apdl
  C=A(1,3) A(2,2)=(C+4)/2

  If ``VALUE`` is the table array name, the subscripts are the values of the primary variables and
  ```

  the table is evaluated at these specified index values.

  If blank, delete this parameter. Example:

  ``` apdl
  A=
  ```

  deletes parameter

  ``` apdl
  A
  ```

  ``` apdl
  A
  ```

- `val2, val3, val4, val5, val6, val7, val8, val9, val10 : str` - If `Par` is an array parameter, values `VAL2` through `VAL10` (up to the last nonblank value) are sequentially assigned to the succeeding array elements of the column. Examples:

  ``` apdl
  *SET,A(1,4),10,11
  ```

  assigns

  ``` apdl
  A(1,4)=10, A(2,4)=11
  ```

  ``` apdl
  A(1,4)=10, A(2,4)=11
  ```

  ``` apdl
  *SET,B(2,3),'file10','file11'
  ```

  assigns

  ``` apdl
  B(2,3)='file10',           B(3,3)='file11'
  ```

  ``` apdl
  B(2,3)='file10',           B(3,3)='file11'
  ```

Assigns values to user-named parameters that can be substituted later in the run. The equivalent (and recommended) format is `Par` = `VALUE`, `VAL2`, `VAL3`,..., `VAL10`

which can be used in place of **\*SET**, `Par`,... for convenience.

This command is valid in any processor.

Parameters (numeric or character) can be scalars (single valued) or arrays (multiple valued in one, two, or three dimensions). An unlimited number of parameter names can be defined in any run. For very large numbers of parameters, it is most efficient to define them in alphabetical order.

Parameter values can be redefined at any time. Array parameters can also be assigned values within a do-loop ( `*DO` ) for convenience. Internally programmed do-loop commands are also available with the **\*V** `XX` commands ( [[vfill|*VFILL]] ). Parameter values (except for parameters ending in an underscore) can be listed with the [[starstatus|*STATUS]] command, displayed via [[starvplot|*VPLOT]] (numeric parameters only), and modified via `*VEDIT` (numeric parameters only).

Older program-provided macro files can use parameter names that do not begin with an underscore. Using these macros embedded in your own macros may cause conflicts if the same parameter names are used.

Parameters can also be resolved in comments created via [[com|/COM]]. A parameter can be deleted by redefining it with a blank `VALUE`. If the parameter is an array, the entire array is deleted. Parameters can also be defined by a response to a query via `*ASK` or from a Mechanical APDL- provided value via [[get|*GET]].

Array parameters must be dimensioned ( [[dim|*DIM]] ) before being assigned values unless they are the result of an array operation or defined using the implied loop convention.

Undefined scalar parameters are initialized to a near-zero value. Numeric array parameters are initialized to zero when dimensioned, and character array parameters are initialized to blank.

An existing array parameter must be deleted before it can be redimensioned.

Array parameter names must be followed by a subscript list (enclosed in parentheses) identifying the element of the array. The subscript list can have one, two, or three values (separated by commas). Typical array parameter elements are A(1,1), NEW_VAL(3,2,5), RESULT(1000). Subscripts for defining an array element must be integers (or parameter expressions that evaluate to integers). Non-integer values are rounded to the nearest integer value.

All array parameters are stored as 3D arrays with the unspecified dimensions set to 1. For example, the 4th array element of a 1-dimensional array, A(4), is stored as array element A(4,1,1).

Arrays adhere to standard FORTRAN conventions.

If the parameter name `Par` is input in a numeric argument of a command, the numeric value of the parameter (as assigned with **\*SET**, [[get|*GET]], =, etc.) is substituted into the command at that point. Substitution occurs only if the parameter name is used between blanks, commas, parentheses, or arithmetic operators (or any combination) in a numeric argument. Substitution can be prevented by enclosing the parameter name `Par` within single quotes ( ' ), if the parameter is alone in the argument; if the parameter is part of an arithmetic expression, the entire expression must be enclosed within single quotes to prevent substitution. In either case the character string will be used instead of the numeric value (and the string will be taken as 0.0 if it is in a numeric argument).

A forced substitution is available in the text fields of [[title|/TITLE]], [[stitle|/STITLE]], [[tlabel|/TLABEL]], [[an3d|/AN3D]], [[syp|/SYP]] ( `ARG1` - `ARG8` ), and [[abbr|*ABBR]] by enclosing the parameter within percent (%) signs. Also, parameter substitution can be forced within the file name or extension fields of commands having these fields by enclosing the parameter within percent (%) signs. Array parameters ( [[dim|*DIM]] ) must include a subscript (within parentheses) to identify the array element whose value is to be substituted, such as A(1,3). Out-of-range subscripts result in an error message. Non-integer subscripts are allowed when identifying a TABLE array element for substitution. A proportional linear interpolation of values among the nearest array elements is performed before substitution. Interpolation is done in all three dimensions.

Interpolation is based upon the assigned index numbers which must be defined when the table is filled ( [[dim|*DIM]] ).

Most alphanumeric arguments permit the use of character parameter substitution. When the parameter name `Par` input, the alphanumeric value of the parameter is substituted into the command at that point. Substitution can be suppressed by enclosing the parameter name within single quotes ( ' ). Forced substitution is available in some fields by enclosing the parameter name within percent (%) signs. Valid forced substitution fields include command name fields, `Fname` (filename) or `Ext` (extension) arguments, [[abbr|*ABBR]] command ( `Abbr` arguments), [[title|/TITLE]] and [[stitle|/STITLE]] commands ( `Title` argument) and [[tlabel|/TLABEL]] command ( `Text` argument). Character parameter substitution is also available in the `*ASK`, [[an3d|/AN3D]], [[cfwrite|*CFWRITE]], `*IF`, `*ELSEIF`, [[msg|*MSG]], **\*SET**, [[use|*USE]], [[vread|*VREAD]], and [[vwrite|*VWRITE]] commands. Character array parameters must include a subscript (within parentheses) to identify the array element whose value is to be substituted.

If a parameter operation expression is input in a numeric argument, the numeric value of the expression is substituted into the command at that point. Allowable operation expressions are of the form

``` apdl
E1oE2oE3...oE10
```

where E1, E2, etc. are expressions connected by operators (o). The allowable operations (o) are

``` apdl
+ - * / ** < >
```

For example,

``` apdl
A+B**C/D*E
```

is a valid operation expression. The

``` apdl
*
```

represents multiplication and the

``` apdl
**
```

represents exponentiation.

Exponentiation of a negative number (without parentheses) to an integer power follows standard FORTRAN hierarchy conventions; that is, the positive number is exponentiated and then the sign is attached. Thus, -4\*\*2 is evaluated as -16. If parentheses are applied, such as (-4)\*\*2, the result is 16.

A parameter is evaluated as a number within parentheses before exponentiation. Exponentiation of a negative number to a non-integer power is performed by exponentiating the positive number and prepending the minus sign, for example, -4\*\*2.3 is -(4\*\*2.3). The \< and \> operators allow conditional substitution. For example, E1\<E2 substitutes the value of E1 if the comparison is true or the value of E2 if the comparison is false.

Do not use spaces around operation symbols, as " *" (a space and a star) makes the remainder of the line a comment. Operation symbols (or symbols and signs) cannot be immediately adjacent to each other. Parentheses can be used to separate symbols and signs, to determine a hierarchy of operations, or for clarity. For example, use A(-B) instead of A*\*-B. Numbers ending with +0nn or -0nn are assumed to be of exponential form (as written on files by some computer systems) so that 123-002 is 123E-2 while 123-2 is 121. Avoid inputting this form of exponential data directly. The default hierarchy follows the standard FORTRAN conventions, namely:

- operations in parentheses (innermost first)
- then exponentiation (right to left)
- then multiplication or division (left to right)
- then unary association (such as +A or -A)
- then addition or subtraction (left to right)
- then logical evaluations (left to right).

Expressions (E) can be a constant, a parameter, a function, or another operation expression (of the form E1oE2oE3...oE10). Functions are of the form FTN(A) where the argument (A) can itself be of the form E1oE2oE3...oE10. Operations are recursive to a level of four deep (three levels of internally nested parentheses). Iterative floating point parameter arithmetic should not be used for high precision input because of the accumulated numerical round off-error. Up to 10 expressions are accepted within a set of parenthesis.

Valid functions (which are based on standard FORTRAN functions where possible) are:

(table not available in the PyMAPDL source, see the Ansys help page)

Function arguments ( X, Y, etc.) must be enclosed within parentheses and can be numeric values, parameters, or expressions. Input arguments for angular functions must evaluate to radians by default. Output from angular functions are also in radians by default. See [[afun|*AFUN]] to use degrees instead of radians for the angular functions. See [[vfun|*VFUN]] for applying these parameter functions to a sequence of array elements. Additional functions, called get functions, are described via [[get|*GET]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SET_st.html
