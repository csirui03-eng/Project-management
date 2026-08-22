---
apdl: "THOPT"
method: thopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.thopt
generated: 2026-08-22
tags: [mapdl-command]
---

# THOPT

PyMAPDL: `mapdl.thopt(refopt='', reformtol='', ntabpoints='', tempmin='', tempmax='', algo='', **kwargs)`

Specifies nonlinear transient thermal solution options.

## Parameters

**refopt**

Matrix reform option.

- `FULL` - Use the full Newton-Raphson solution option (default). All subsequent input values are ignored.
- `QUASI` - Use a selective reform solution option based on `REFORMTOL`.

**reformtol**: Property change tolerance for Matrix Reformation (.05 default). The thermal matrices are reformed if the maximum material property change in an element (from the previous reform time) is greater than the reform tolerance. Valid only when `Refopt` = QUASI.

**ntabpoints**: Number of points in Fast Material Table (64 default). Valid only when `Refopt` = QUASI.

**tempmin**: Minimum temperature for Fast Material Table. Defaults to the minimum temperature defined by the [[mptemp|MPTEMP]] command for any material property defined. Valid only when `Refopt` = QUASI.

**tempmax**: Maximum temperature for Fast Material Table. Defaults to the maximum temperature defined by the [[mptemp|MPTEMP]] command for any material property defined. Valid only when `Refopt` = QUASI.

**algo**

Specifies which solution algorithm to apply:

- `0` - Multipass (default).
- `1` - Iterative.

Valid only when `Refopt` = QUASI.

## Notes

The QUASI matrix reform option is supported by the ICCG, JCG, PCG, and sparse solvers only ( [[eqslv|EQSLV]] ). The Quasi method is an approximation to the FULL method and will not be as accurate when the nonlinearity is strong. However, you can control the inaccuracy by using small time steps.

For `Refopt` = QUASI:

- Results from a restart may be different than results from a single run because the stiffness matrices are always recreated in a restart run, but may or may not be in a single run (depending on the behavior resulting from the `REFORMTOL` setting). Additionally, results may differ between two single runs as well, if the matrices are reformed as a result of the `REFORMTOL` setting.

For more information, see [Solution Algorithms Used in Transient Thermal Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/thermsolualgors.html#therm_fullquasirad)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_THOPT.html
