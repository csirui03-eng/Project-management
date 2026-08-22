---
apdl: "ARCLEN"
method: arclen
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.arclen
generated: 2026-08-22
tags: [mapdl-command]
---

# ARCLEN

PyMAPDL: `mapdl.arclen(key='', maxarc='', minarc='', **kwargs)`

Activates the arc-length method.

## Parameters

**key**

Arc-length key:

- `OFF` - Do not use the arc-length method (default).
- `ON` - Use the arc-length method.

**maxarc**: Maximum multiplier of the reference arc-length radius (default = 25).

**minarc**: Minimum multiplier of the reference arc-length radius (default = 1/1000).

## Notes

Activates the arc-length method and sets the minimum and maximum multipliers for controlling the arc-length radius based on the initial arc-length radius.

The initial arc-length radius, t<sub>0</sub>, is proportional (in absolute value) to the initial load factor. The initial load factor is given by:

Initial Load Factor = `TIME` / `NSBSTP`

where `TIME` is the time specified by the [[time|TIME]] command for the arc-length load step, and `NSBSTP` is the number of substeps specified by the [[nsubst|NSUBST]] command.

The factors `MAXARC` and `MINARC` are used to define the range for the arc-length radius to expand and shrink during the substep solution:

- t <sub>MAX</sub> = `MAXARC` \* t <sub>0</sub>
- t <sub>MIN</sub> = `MINARC` \* t <sub>0</sub>

In each substep, the arc-length radius is kept constant throughout the equilibrium iterations. After each converged substep, the arc-length radius for the next substep is modified depending on the convergence behavior. If the substep converges and the program heuristic predicts an easy convergence, the arc-length radius is enlarged. If the enlarged value is greater than t<sub>MAX</sub>, the arc-length radius is reset to t<sub>MAX</sub>. If the substep does not converge, bisection will take place until the arc-length radius is reduced to t<sub>MIN</sub>. If further nonconvergence is encountered, the solution terminates.

The arc-length method predicts the next time increment (that is, load factor increment). Therefore, the [[autots|AUTOTS]] and [[pred|PRED]] commands are ignored when the arc-length method is used.

The [[stabilize|STABILIZE]] and [[lnsrch|LNSRCH]] commands are also ignored.

The arc-length method cannot be used in a multiframe restart.

For difficult problems, one suggestion is to increase the initial number of substeps ( [[nsubst|NSUBST]] ), and to prevent the arc-length radius from increasing too rapidly ( `MAXARC` = 1).

**ARCLEN** cannot be used for any load step that has no applied load or displacement.

The arc-length method does not support tabular loads. In order to use the arc-length method, you must replace tabular loads by other load types and then run the analysis again.

The arc-length method can only be used with the sparse solver ( [[eqslv|EQSLV]],SPARSE). If any other solver is specified, the solver method is automatically changed to sparse, and a warning message is issued to notify you.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ARCLEN.html
