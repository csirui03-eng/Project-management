---
apdl: "ACCOPTION"
method: accoption
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.accoption
generated: 2026-08-22
tags: [mapdl-command]
---

# ACCOPTION

PyMAPDL: `mapdl.accoption(activate='', **kwargs)`

Specifies GPU accelerator capability options.

## Parameters

**activate**

Activates the GPU accelerator capability within the equation solvers.

- `OFF` - Do not use GPU accelerator.
- `ON` - Use GPU accelerator.

## Notes

### Argument descriptions

- `activate : str` - Activates the GPU accelerator capability within the equation solvers.
  - `OFF` - Do not use GPU accelerator.
  - `ON` - Use GPU accelerator.

The GPU accelerator capability requires specific hardware to be installed on the machine. See the appropriate Ansys, Inc. Installation Guide ( Windows or Linux ) for a list of supported GPU hardware. Use of this capability also requires HPC licensing. For more information, see [GPU Accelerator Capability](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_dan/gputrouble.html)

The GPU accelerator capability is available for the sparse direct solver and the PCG and JCG iterative solvers. Static, buckling, modal, full harmonic, and full transient analyses are supported. For buckling analyses, the Block Lanczos and Subspace eigensolvers are supported. For modal analyses, only the Block Lanczos, PCG Lanczos, Subspace, Unsymmetric, and Damped eigensolvers are supported. Activating this capability when using other equation solvers or other analysis types has no effect.

The GPU accelerator capability is supported only on the Windows 64-bit and Linux 64-bit platforms.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ACCOPTION.html
