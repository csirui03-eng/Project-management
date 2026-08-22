---
apdl: "PSCONTROL"
method: pscontrol
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.pscontrol
generated: 2026-08-22
tags: [mapdl-command]
---

# PSCONTROL

PyMAPDL: `mapdl.pscontrol(option='', key='', **kwargs)`

Enables or disables shared-memory parallel operations.

**Command default:** None. The command is ignored if issued with no arguments.

## Parameters

**option**

Specify the operations for which you intend to enable/disable parallel behavior:

- `ALL` - Enable/disable parallel for all areas (default).
- `PREP` - Enable/disable parallel during preprocessing ( [[prep7|/PREP7]] ).
- `SOLU` - Enable/disable parallel during solution ( [[slashsolu|/SOLU]] ).
- `FORM` - Enable/disable parallel during element matrix generation.
- `SOLV` - Enable/disable parallel during equation solver.
- `RESU` - Enable/disable parallel during element results calculation.
- `POST` - Enable/disable parallel during postprocessing ( [[post1|/POST1]] and [[post26|/POST26]] ).
- `STAT` - List parallel operations that are enabled/disabled.

**key**

Option control key. Used for all `Option` values except STAT.

- `ON` - Enable parallel operation.
- `OFF` - Disable parallel operation.

## Notes

Use this command in shared-memory parallel operations.

This command is useful when you encounter minor discrepancies in a nonlinear solution when using different numbers of processors. A parallel operation applied to the element matrix generation can produce a different nonlinear solution with a different number of processors. Although the nonlinear solution converges to the same nonlinear tolerance, the minor discrepancy created may not be desirable for consistency.

Enabling/disabling parallel behavior for the solution ( `Option` = SOLU) supersedes the activation/deactivation of parallel behavior for element matrix generation (FORM), equation solver (SOLV), and element results calculation (RESU).

The SOLV option supports only the sparse direct and PCG solvers ( [[eqslv|EQSLV]],SPARSE or PCG). No other solvers are supported.

This command applies only to shared-memory architecture. It does not apply to distributed-memory parallel processing.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSCONTROL.html
