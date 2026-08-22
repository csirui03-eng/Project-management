---
apdl: "CYCFILES"
method: cycfiles
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.cycfiles
generated: 2026-08-22
tags: [mapdl-command]
---

# CYCFILES

PyMAPDL: `mapdl.cycfiles(fnamerst='', extrst='', fnamerfrq='', extrfrq='', **kwargs)`

Specifies the data files where results are to be found for a cyclic symmetry mode-superposition harmonic analysis.

**Command default:**

No defaults are available for the **CYCFILES** command. You must issue this command to properly postprocess the results of a cyclic symmetry mode-superposition harmonic analysis. If issued with no arguments, the postprocessing will be done using `Jobname.rst` and `Jobname.rfrq` from the current working directory.

## Parameters

**fnamerst**: The file name and directory path of the results file from the cyclic modal solution. Defaults to `Jobname`.

**extrst**: File name extension for `FnameRst`. Defaults to `rst`.

**fnamerfrq**: The file name and directory path of the results file from the cyclic mode-superposition harmonic solution. Defaults to the value of the `FnameRst` argument.

**extrfrq**: File name extension for `FnameRfrq`. Defaults to `rfrq`.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYCFILES.html
