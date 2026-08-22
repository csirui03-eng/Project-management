---
apdl: "KUSE"
method: kuse
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.kuse
generated: 2026-08-22
tags: [mapdl-command]
---

# KUSE

PyMAPDL: `mapdl.kuse(key='', **kwargs)`

Specifies whether or not to reuse factorized matrices.

## Parameters

**key**

Reuse key:

- `0` - Program decides whether or not to reuse the previous factorized matrices.
- `1` - Force the previous factorized matrices to be reused. Used mainly in a restart. Forcing reuse of the matrices is a nonstandard use of the program and should be done with caution. For instance, using this option and changing the number of elements, or the number or type of degrees of freedom, may cause an abort.
- `-1` - All element matrices are reformed and are used to reform new factorized matrices.

## Notes

Overrides the program logic to determine whether or not to reuse the previous factorized matrices for each substep of this load step. Applies only to static or full transient analyses. For more details see.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KUSE.html
