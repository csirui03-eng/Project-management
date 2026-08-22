---
apdl: "GAUGE"
method: gauge
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.gauge
generated: 2026-08-22
tags: [mapdl-command]
---

# GAUGE

PyMAPDL: `mapdl.gauge(opt='', freq='', **kwargs)`

Gauges the problem domain for a magnetic edge-element formulation.

## Parameters

**opt**

Type of gauging to be performed:

- `ON` - Perform tree gauging of the edge values (default).
- `OFF` - Gauging is off. (You must specify custom gauging via APDL specifications.)
- `STAT` - Gauging status (returns the current `Opt` and `FREQ` values)

**freq**

The following options are valid when `Opt` = ON:

- `0` - Generate tree-gauging information once, at the first load step. Gauging data is retained for subsequent load steps. (This behavior is the default.)
- `1` - Repeat gauging for each load step. Rewrites the gauging information at each load step to accommodate changing boundary conditions on the AZ degree of freedom (for example, adding or deleting AZ constraints via the [[d|D]] or [[ce|CE]] commands).

## Notes

The **GAUGE** command controls the tree-gauging procedure required for electromagnetic analyses using an edge-based magnetic formulation (elements `SOLID226`, `SOLID227`, `SOLID236` and `SOLID237` ).

Gauging occurs at the solver level for each solution ( [[solve|SOLVE]] ). It sets additional zero constraints on the edge-flux degrees of freedom AZ to produce a unique solution; the additional constraints are removed after solution.

Use the `FREQ` option to specify how the command generates gauging information for multiple load steps.

Access the gauging information via the TGAUGE component of gauged nodes. The program creates and uses this component internally to remove and reapply the AZ constraints required by gauging. If `FREQ` = 0, the TGAUGE component is created at the first load step and is used to reapply the tree gauge constraints at subsequent load steps. If `FREQ` = 1, the tree-gauging information and the TGAUGE component are generated at every load step

If gauging is turned off ( **GAUGE**,OFF), you must specify your own gauging at the APDL level.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GAUGE.html
