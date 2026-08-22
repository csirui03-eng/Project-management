---
apdl: "*STATUS"
method: starstatus
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.starstatus
generated: 2026-08-22
tags: [mapdl-command]
---

# *STATUS

PyMAPDL: `mapdl.starstatus(par='', imin='', imax='', jmin='', jmax='', kmin='', kmax='', lmin='', lmax='', mmin='', mmax='', kpri='', **kwargs)`

Lists the current parameters and abbreviations.

## Parameters

**par**

Specifies the parameter or sets of parameters listed. For array parameters, use `IMIN`, `IMAX`, etc. to specify ranges. Use [[dim|*DIM]] to define array parameters. Use `*VEDIT` to review array parameters interactively. Use [[vwrite|*VWRITE]] to print array values in a formatted output. If `Par` is blank, list all scalar parameter values, array parameter dimensions, and abbreviations. If ARGX, list the active set of local macro parameters (ARG1 to ARG9 and AR10 to AR99) ( [[use|*USE]] ).

The following are possible values for `Par`

- `ALL or blank` - Lists all parameters (except local macro parameters and those with names beginning or ending with an underbar) and toolbar abbreviations.
- `_PRM` - Lists only parameters with names beginning with an underbar (\_). These are Mechanical APDL internal parameters.
- `PRM_` - Lists only parameters with names ending with an underbar (\_). A good APDL programming convention is to ensure that all parameters created by your system programmer are named with a trailing underbar.
- `ABBR` - Lists all toolbar abbreviations.
- `PARM` - Lists all parameters (except local macro parameters and those with names beginning or ending with an underbar).
- `MATH` - Lists all APDL Math parameters, including vectors, matrices, and linear solvers.
- `PARNAME` - Lists only the parameter specified. `PARNAME` cannot be a local macro parameter name.
- `ARGX` - Lists all local macro parameter values (ARG1- AR99) that are non-zero or non-blank.

**imin**, **imax**, **jmin**, **jmax**, **kmin**, **kmax**, **lmin**, **lmax**, **mmin**, **mmax**: Range of array elements to display (in terms of the dimensions (row, column, plane, book, and shelf). Minimum values default to 1. Maximum values default to the maximum dimension values. Zero may be input for `IMIN`, `JMIN`, and `KMIN` to display the index numbers. See [[taxis|*TAXIS]] command to list index numbers of 4- and 5-D tables.

**kpri**

Use this field to list your primary variable labels (X, Y, Z, TIME, etc.).

- `1` - List the labels (default). YES, Y, or ON are also valid entries.
- `0` - Do not list the labels. NO, N, or OFF are also valid entries.

## Notes

You cannot obtain the value for a single local parameter (for example, **\*STATUS**,ARG2). You can only request all local parameters simultaneously using **\*STATUS**,ARGX.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_STATUS_st.html
