---
apdl: "LANBOPTION"
method: lanboption
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.lanboption
generated: 2026-08-22
tags: [mapdl-command]
---

# LANBOPTION

PyMAPDL: `mapdl.lanboption(strmck='', altmeth='', memory_option='', **kwargs)`

Specifies Block Lanczos eigensolver options.

## Parameters

**strmck**

Controls whether the Block Lanczos eigensolver will perform a Sturm sequence check:

- `OFF` - Do not perform the Sturm sequence check (default).
- `ON` - Perform a Sturm sequence check. This requires additional matrix factorization (which can be expensive), but does help ensure that no modes are missed in the specified range.

**altmeth**: - `ALT1` - Alternative version of the Block Lanczos eigensolver for more difficult modal or buckling problems. This version of Block Lanczos only runs in shared-memory parallel (SMP) mode. If the analysis is run in distributed-memory parallel (DMP) mode, it will switch to SMP mode when this Alternative Block Lanczos solver is invoked, and resume in DMP mode after the eigensolution.

**memory_option**

Memory allocation option:

- `DEFAULT` - Default memory configuration (default). Everything is determined dynamically with respect to current machine resources.
- `INCORE` - Fully in-core memory configuration.
- `MIX1` - First level of mixed in-core / out-of-core configuration.
- `MIX2` - Second level of mixed in-core / out-of-core configuration.
- `OUTOFCORE` - Fully out-of-core memory configuration.

## Notes

**LANBOPTION** specifies options to be used with the Block Lanczos eigensolver during an eigenvalue buckling analysis ( [[bucopt|BUCOPT]],LANB) or a modal analysis ( [[modopt|MODOPT]],LANB).

For more difficult eigenproblems, `AltMeth` = ALT1 could achieve better converged eigensolutions at the cost of more computing time. This ALT1 option is useful for double-checking solution accuracy. It should be used for difficult eigenproblems like those with many duplicated eigenmodes, or eigen-buckling problems with very thin beam/shell structures.

**Memory Allocation Option**

The Block Lanczos eigensolver algorithm allocates two main pools of memory:

Memory for the internal sparse solver iterations.

Memory for the specific Lanczos working arrays.

The following table shows how memory is allocated for each option.

(table not available in the PyMAPDL source, see the Ansys help page)

The MIX1 configuration typically uses more memory than the MIX2 configuration, except when a large number of modes are requested for a small model.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LANBOPTION.html
