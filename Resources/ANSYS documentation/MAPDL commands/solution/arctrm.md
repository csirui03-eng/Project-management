---
apdl: "ARCTRM"
method: arctrm
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.arctrm
generated: 2026-08-22
tags: [mapdl-command]
---

# ARCTRM

PyMAPDL: `mapdl.arctrm(lab='', val='', node='', dof='', **kwargs)`

Controls termination of the solution when the arc-length method is used.

## Parameters

**lab**

Specifies the basis of solution termination:

- `OFF` - Does not use **ARCTRM** to terminate analysis (default).
- `L` - Terminates the analysis if the first limit point has been reached. The first limit point is that point in the response history when the tangent stiffness matrix becomes singular (that is, the point at which the structure becomes unstable). If `Lab` = L, arguments `VAL`, `NODE`, `DOF` are ignored.
- `U` - Terminates the analysis when the displacement first equals or exceeds the maximum desired value.

**val**: Maximum desired displacement (absolute value). Valid only if `Lab` = U. The analysis terminates whenever the calculated displacement first equals or exceeds this value. For rotational degrees of freedom, `VAL` must be in radians (not degrees).

**node**: Node number corresponding to displacement used to compare with displacement specified by `VAL`. If blank, the maximum displacement will be used. Valid only if `Lab` = U.

**dof**: Valid degree of freedom label for nodal displacement specified by `NODE`. Valid labels are UX, UY, UZ, ROTX, ROTY, ROTZ. Valid only if `NODE` \>0 and `Lab` = U.

## Notes

The **ARCTRM** command is valid only when the arc-length method ( [[arclen|ARCLEN]],ON) is used.

It can be convenient to use this command to terminate the analysis when the first limit point is reached. In addition, the [[ncnv|NCNV]] command should be used to limit the maximum number of iterations. If the **ARCTRM** command is not used, and the applied load is so large that the solution path can never reach that load, the arc-length solution will continue to run until a CPU time limit or a "maximum number of iterations" is reached.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ARCTRM.html
