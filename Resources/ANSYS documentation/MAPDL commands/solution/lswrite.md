---
apdl: "LSWRITE"
method: lswrite
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_operations.LoadStepOperations.lswrite
generated: 2026-08-22
tags: [mapdl-command]
---

# LSWRITE

PyMAPDL: `mapdl.lswrite(lsnum='', **kwargs)`

Writes load and load step option data to a file.

> [!WARNING]
> This command must be run using `non_interactive <ansys.mapdl.core.Mapdl.non_interactive>`. Please visit [Unsupported Interactive Commands](https://mapdl.docs.pyansys.com/version/stable/user_guide/mapdl.html#unsupported-interactive-commands) for further information.

## Parameters

**lsnum**: Number to be assigned to the load step file name for identification purposes. Defaults to 1 + highest `LSNUM` used in the current session. Issue **LSWRITE**,STAT to list the current value of `LSNUM`. Issue **LSWRITE**,INIT to reset to 1. The load step file will be named `Jobname.Sn`, where `n` is the specified `LSNUM` value (preceded by "0" for values 1-9). On systems with a 3-character limit on the file name extension, the "S" is dropped for `LSNUM` \> 99.

## Notes

Writes all load and load step option data for the selected model to a load step file for later use. **LSWRITE** does not capture changes made to real constants ( [[r|R]] ), material properties ( [[mp|MP]] ), couplings ( [[cp|CP]] ), or constraint equations ( [[ce|CE]] ).

Solid model loads will not be saved if the model is not meshed. Solid model loads, if any, are transferred to the finite element model. Issue [[lsclear|LSCLEAR]],FE to delete finite element loads.

One file is written for each load step. Use the [[lsread|LSREAD]] command to read a single load step file, and the [[lsdele|LSDELE]] command to delete load step files. Use the [[lssolve|LSSOLVE]] command to read and solve the load steps sequentially.

Solution control commands are typically not written to the file unless you specifically change a default solution setting.

**LSWRITE** does not support the following commands: [[dj|DJ]], [[fj|FJ]], [[gsbdata|GSBDATA]], [[gsgdata|GSGDATA]], [[estif|ESTIF]], [[ekill|EKILL]], [[ealive|EALIVE]], [[mpchg|MPCHG]], and [[outres|OUTRES]]. These commands will not be written to the load step file.

**LSWRITE** cannot be used with the birth-death option.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSWRITE.html
