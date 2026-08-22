---
apdl: "HROPT"
method: hropt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.hropt
generated: 2026-08-22
tags: [mapdl-command]
---

# HROPT

PyMAPDL: `mapdl.hropt(method='', value1='', value2='', value3='', value4='', value5='', **kwargs)`

Specifies harmonic analysis options.

## Parameters

**method**

Solution method for the harmonic analysis:

- `AUTO` - Automatically select the most efficient method (default). Either the full method (FULL) or the frequency-sweep method (VT) is selected, depending on the model. For `Method` = AUTO, `Value1`.. `Value5` are unused fields.

- `FULL` - Full method. For `Method` = AUTO, `Value1`.. `Value5` are unused fields.

- `MSUP` - Mode-superposition method. See .

- `VT` - Frequency-sweep (Variational Technology) method (based on the FULL harmonic algorithm). See .

- `VTPA` - Frequency-sweep (Variational Technology) perfect absorber method (based on the FULL harmonic algorithm). See .

- `KRYLOV` - Frequency-sweep Krylov method. See .

  The Krylov approximation can be run using macros as customizable templates as described in. Alternatively, you can perform a Krylov solution without customization as described in [Krylov Method Implemented using Mechanical APDL Commands](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_Krysweep.html#str_kryClist)

If the solution method is not specified, the program automatically selects either the Full method or the frequency-sweep method, depending on which method is most efficient for the model. The frequency-sweep method uses the underlying Variational Technology method.

**value1**, **value2**, **value3**, **value4**, **value5**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HROPT.html) for further information.

## Notes

Specifies the method of solution for a harmonic analysis ( [[antype|ANTYPE]],HARMIC).

If used in SOLUTION, this command is valid only within the first load step.

This command is also valid in PREP7.

**For** `Method` = MSUP:

- For cyclic symmetry mode-superposition harmonic solutions, `MAXMODE` and `MINMODE` are ignored.
- To include [residual vectors](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR_SMSUP.html#ans_str_moda_resresp) in your [mode-superposition harmonic analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR4_MODESUPER.html#aMhQxq6emcm), specify [[resvec|RESVEC]],ON.
- `MAXMODE` and `MINMODE` are ignored after a modal restart analysis where remote modal files usage ( [[moddir|MODDIR]] ) and residual vector calculation ( [[resvec|RESVEC]],ON) have been activated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HROPT.html
