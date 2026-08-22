---
apdl: "CJUMP"
method: cjump
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.cjump
generated: 2026-08-22
tags: [mapdl-command]
---

# CJUMP

PyMAPDL: `mapdl.cjump(option='', input1='', input2='', input3='', input4='', input5='', input6='', input7='', input8='', **kwargs)`

Initiates a [cycle-jump analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advcycjumpmethod.html#).

**Command default:**

Cycle jump analysis is disabled.

## Parameters

**option**

Option to be applied:

- `CRIT` - Jump criterion.
- `INTENT` - Declaration of cycle jump analysis intent. For an analysis that begins with a standard solution, specify before the first [[solve|SOLVE]] command.
- `MINCYC` - Minimum number of cycles before a jump is allowed (and, if desired, the [empirical adjustment of minimum intermediate cycles](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advcycjumpmethod.html#eq913e29a3-98a9-46aa-a8b0-e222d972a0cf) ).
- `INICYC` - Minimum number of initial cycles before a jump is allowed.
- `MAXJUMP` - Maximum allowable jump.
- `RELTIME` - Relative time.
- `CONTROL` - Control-variable selection.
- `CNMT` - Material-ID-dependent jump control.
- `ADCR` - Material-ID- and/or control-variable-dependent jump criteria.
- `CALC` - Jump-calculation option.
- `PERC` - Statistical-jump calculation.
- `OUTP` - Diagnostic information output.

**input1**: Additional input according to the specified Option : This command contains some tables and extra information which can be inspected in the original documentation pointed above.

**input2**, **input3**, **input4**, **input5**, **input6**, **input7**, **input8**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CJUMP.html) for further information.

## Notes

When `Option` = CONTROL, any input of a control variable replaces the default (S). If stress is also needed in combination with another control variable (or variables), you must specify it explicitly.

**CJUMP** requires a corresponding cyclic loading analysis ( [[cload|CLOAD]] ).

For more information, see [Cycle-Jump Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advcycjumpmethod.html#)

This command is also valid in PREP7 ( [[prep7|/PREP7]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CJUMP.html
