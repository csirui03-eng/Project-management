---
apdl: "SEEXP"
method: seexp
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.seexp
generated: 2026-08-22
tags: [mapdl-command]
---

# SEEXP

PyMAPDL: `mapdl.seexp(sename='', usefil='', imagky='', expopt='', **kwargs)`

Specifies options for the substructure expansion pass.

## Parameters

**sename**: The name (case-sensitive) of the superelement matrix file created by the substructure generation pass ( `Sename.SUB` ). Defaults to the initial jobname `File`. If a number, it is the element number of the superelement as used in the use pass.

**usefil**: The name of the file containing the superelement degree-of-freedom (DOF) solution created by the substructure use pass ( `Usefil.DSUB` ).

**imagky**

Key to specify use of the imaginary component of the DOF solution. Applicable only if the use pass is a harmonic ( [[antype|ANTYPE]],HARMIC) analysis:

- `OFF` - Use real component of DOF solution (default).
- `ON` - Use imaginary component of DOF solution.

> If all solutions are to be expanded ( [[numexp|NUMEXP]],ALL), `Imagky` is ignored and both the real

and imaginary solutions are expanded.

**expopt**

Key to specify whether the superelement ( [[antype|ANTYPE]] ,SUBSTR) expansion pass ( [[expass|EXPASS]],ON) should transform the geometry:

- `OFF` - Do not transform node or element locations (default).
- `ON` - Transform node or element locations in the FE geometry record of the `.rst` results file.

## Notes

Specifies options for the expansion pass of the substructure analysis ( [[antype|ANTYPE]],SUBSTR). If used in SOLUTION, this command is valid only within the first load step.

If you specify geometry transformation ( `Expopt` = ON), you must retrieve the transformation matrix (if it exists) from the specified `.SUB` file. The command updates the nodal X, Y, and Z coordinates to represent the transformed node locations. The `Expopt` option is useful when you want to expand superelements created from other superelements (via [[setran|SETRAN]] or [[sesymm|SESYMM]] commands). For more information, see and.

This command is also valid in [[prep7|/PREP7]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SEEXP.html
