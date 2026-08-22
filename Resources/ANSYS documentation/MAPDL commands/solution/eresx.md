---
apdl: "ERESX"
method: eresx
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.eresx
generated: 2026-08-22
tags: [mapdl-command]
---

# ERESX

PyMAPDL: `mapdl.eresx(key='', **kwargs)`

Specifies extrapolation of integration-point results.

**Command default:**

Extrapolate integration-point results to the nodes for all elements except those with active plasticity, creep, or swelling nonlinearities (default).

For coupled pore-pressure-thermal elements ( `CPT212`, `CPT213`, `CPT215`, `CPT216`, `CPT217` ), the default behavior is to copy integration-point results to the nodes.

## Parameters

**key**

Extrapolation key:

- `DEFA` - If element is fully elastic (no active plasticity, creep, or swelling nonlinearities), extrapolate the integration-point results to the nodes. If any portion of the element is plastic (or other active material nonlinearity), copy the integration-point results to the nodes (default).
- `YES` - Extrapolate the linear portion of the integration-point results to the nodes and copy the nonlinear portion (for example, plastic strains).
- `NO` - Copy the integration-point results to the nodes.

## Notes

Specifies whether the solution results at the element-integration points are extrapolated or copied to the nodes for element and nodal postprocessing. Structural stresses, elastic and thermal strains, field gradients, and fluxes are affected. Nonlinear data (such as plastic, creep, and swelling strains) are always copied to the nodes, never extrapolated. For shell elements, **ERESX** applies only to integration-point results in the in-plane directions.

Extrapolation occurs in the element-solution coordinate system. For elements allowing different solution systems at integration points (such as `SHELL281` and `SOLID186` ), extrapolation can produce unreliable results when the solution coordinate systems in each element differ significantly. (Varying element-solution coordinate systems can be created via the [[esys|ESYS]] command or from large deformation.) Examine results carefully in such cases, and disable extrapolation if necessary.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ERESX.html
