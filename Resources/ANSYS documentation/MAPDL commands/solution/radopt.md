---
apdl: "RADOPT"
method: radopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.radiosity.Radiosity.radopt
generated: 2026-08-22
tags: [mapdl-command]
---

# RADOPT

PyMAPDL: `mapdl.radopt(fluxtol='', solver='', maxiter='', toler='', overrlex='', maxfluxiter='', conservation='', **kwargs)`

Specifies Radiosity Solver options.

## Parameters

**fluxtol**: Convergence tolerance for radiation flux. Defaults to 0.0001. This value is a relative tolerance.

**solver**

Choice of solver for radiosity calculation:

- `0` - Gauss-Seidel iterative solver.
- `1` - Direct solver.
- `2` - Jacobi iterative solver (default).

**maxiter**: Maximum number of iterations for the iterative solvers ( `SOLVER` = 0 or 2). Defaults to 1000.

**toler**

Convergence tolerance for the iterative solvers ( `SOLVER` = 0 or 2). Defaults to 0.1.

If `TOLER` ≥ 0, the value is interpreted as an absolute tolerance. If `TOLER` \< 0, it is interpreted as a relative tolerance.

**overrlex**: Over-relaxation factor applied to the iterative solvers ( `SOLVER` = 0 or 2). Defaults to 0.1.

**maxfluxiter**

Maximum number of flux iterations to be performed according to the specified solver type:

- `0` - If the FULL solver is specified ( [[thopt|THOPT]],FULL), convergence criteria are monitored and iterations are performed until convergence occurs. If the QUASI solver is specified ( [[thopt|THOPT]],QUASI), convergence criteria are ignored and one iteration is performed. This value is the default.
- `1, 2, 3,...N` - If the FULL solver is specified ( [[thopt|THOPT]],FULL), convergence criteria are monitored and iterations are performed until convergence occurs, or until the specified number of iterations has been completed, whichever comes first. If the QUASI solver is specified ( [[thopt|THOPT]],QUASI), convergence criteria are ignored and the specified number of iterations are completed.

To view `MAXFLUXITER` usage illustrations, see and.

**conservation**

Key to account for the midside node temperature of underlying solid elements for radiosity calculations. Under normal circumstations using lower order elements, this option does not need to be activated. However, when using higher elements, you can improve energy conservation by setting `CONSERVATION` = 1.

- `0` - Not active (default). The midside node temperatures are not accounted for in the radiosity calculations.
- `1` - Active. The midside node temperatures are accounted for in the radiosity calculations. To work effectively, `CONSERVATION` requires a one-to-one correspondance between the surface elements and their underlying solid elements. Therefore, it cannot be activated if the [[rdec|RDEC]] command was issued when generating `SURF251` or `SURF252` elements.

## Notes

The radiation heat flux is linearized, resulting in robust convergence.

The radiation flux norm for `FLUXTOL` is expressed as:

(equation not available in the PyMAPDL source, see the Ansys help page)

where i is the pass or iteration number and j is the surface facet for radiation.

For a sufficiently small absolute tolerance value, relative tolerance converges in fewer iterations than absolute tolerance. For a sufficiently large absolute tolerance value, relative tolerance may cause convergence difficulties.

For more information about `FLUXTOL` and `MAXFLUXITER` usage, see and in the [Thermal Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/Hlp_G_THE4.html).

In and (under [Solving for Temperature and Radiosity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/thermsolualgors.html#the_trans_quasimethfig) <sub>Q</sub> Q = F<sub>Q</sub> equation system via the iterative method.

If `TOLER` ≥ 0, the iterative solver ( `SOLVER` = 0 or 2) is converged for maximum value over a different `j` as shown:

(equation not available in the PyMAPDL source, see the Ansys help page)

If `TOLER` \< 0, the iterative solver ( `SOLVER` = 0 or 2) is converged for maximum value over a different `j` as shown:

(equation not available in the PyMAPDL source, see the Ansys help page)

where:

- `j` = number of radiation facets
- `k` = number of iterations ( `k` = 1 to `MAXITER` )

The Jacobi iterative solver ( `SOLVER` = 2) is the only solver choice that runs in a fully distributed parallel fashion. Therefore, it is typically the best choice for optimal performance when running in distributed-memory parallel mode.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RADOPT.html
