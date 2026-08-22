---
apdl: "CAMPBELL"
method: campbell
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.campbell
generated: 2026-08-22
tags: [mapdl-command]
---

# CAMPBELL

PyMAPDL: `mapdl.campbell(action='', **kwargs)`

Prepares the result file for a subsequent Campbell diagram of a prestressed structure.

## Parameters

**action**

Campbell action:

- `NONE` - Do not prepare the result file. This option is the default behavior.
- `RSTP` - Prepare the result file ( `Jobname.RSTP` ) for a subsequent [Campbell diagram](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/Hlp_G_ROTCAMPDIAGS.html#rotgencamp2a) of a prestressed structure.

## Notes

For an analysis involving a prestressed structure, the **CAMPBELL** command specifies whether or not to prepare the result file to support a [Campbell diagram](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/Hlp_G_ROTCAMPDIAGS.html#rotgencamp2a) analysis ( [[prcamp|PRCAMP]] or [[plcamp|PLCAMP]] ).

To prestress a structure, the program performs a static solution before the [linear perturbation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strlinpertother.html) modal solution. For specific information about rotating structures, see [Considerations for Rotating Structures](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strllinpertrotmach.html#str_rot_rotating)

The **CAMPBELL** command requires that modal and static analyses be performed alternately. It works only when the number of static analyses is the same as the number of modal analyses. Any number of analyses can be performed, but the same number of each (static and modal) is expected. The modal solutions are appended in the results file ( `Jobname.RSTP` ).

For an example of **CAMPBELL** command usage, see in the [Rotordynamic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/rotdynappenda.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CAMPBELL.html
