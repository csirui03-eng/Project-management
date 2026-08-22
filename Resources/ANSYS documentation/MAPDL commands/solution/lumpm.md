---
apdl: "LUMPM"
method: lumpm
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.lumpm
generated: 2026-08-22
tags: [mapdl-command]
---

# LUMPM

PyMAPDL: `mapdl.lumpm(key='', keyelt='', **kwargs)`

Specifies a lumped mass matrix formulation.

## Parameters

**key**

Formulation key:

- `OFF` - Use the element-dependent default mass matrix formulation (default).
- `ON` - Use a lumped mass approximation.

**keyelt**

Formulation key for elements with rotational degrees of freedom; applicable only when the lumped mass formulation key is turned on ( `Key` = ON):

- `0 (blank)` - Use direct diagonalization of the element mass matrix (default).
- `1` - Use translational mass only.
- `2` - Use the frame invariant formulation.

## Notes

In a modal analysis, the lumped mass matrix option ( **LUMPM**,ON) is not allowed when using the Supernode mode-extraction method ( [[modopt|MODOPT]],SNODE). The eigensolver will automatically be switched to Block Lanczos (LANB) in this case.

In the use pass of a substructuring analysis, the lumped mass matrix formulation ( **LUMPM**,ON) modifies the superelement mass matrix and may give unexpected results.

The translational mass only option ( **LUMPM**,ON,,1) applies to the following elements: `SHELL181`, `BEAM188`, `BEAM189`, `SHELL208`, `SHELL209`, `SHELL281`, `PIPE288`, `PIPE289`, and `ELBOW290`. The frame invariant formulation ( **LUMPM**,ON,,2) applies only to `BEAM188`, `BEAM189`, `PIPE288`, and `PIPE289` elements.

For more information, see [Lumped Matrices](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_et2.html#eltlimitlump)

This command is also valid in PREP7. If used in SOLUTION, this command is valid only within the first load step.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LUMPM.html
