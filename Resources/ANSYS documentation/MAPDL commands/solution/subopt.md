---
apdl: "SUBOPT"
method: subopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.subopt
generated: 2026-08-22
tags: [mapdl-command]
---

# SUBOPT

PyMAPDL: `mapdl.subopt(option='', value1='', **kwargs)`

Specifies Subspace (SUBSP) eigensolver options.

## Parameters

**option**

One of the following options:

- `STRMCK` - Controls whether a Sturm sequence check is performed.

  Valid input for `Value1` when `Option` = STRMCK:

  - `OFF` - Do not perform Sturm sequence check (default).
  - `ON` - Perform Sturm sequence check.

- `MEMORY` - Controls the memory allocation strategy for the Subspace eigensolver.

  Valid input for `Value1` when `Option` = MEMORY:

  - `DEFAULT` - Default memory configuration (default). Everything is determined dynamically with respect to current machine resources.
  - `INCORE` - Fully in-core memory configuration.
  - `MIX1` - First level of mixed in-core / out-of-core configuration.
  - `MIX2` - Second level of mixed in-core / out-of-core configuration.
  - `OUTOFCORE` - Fully out-of-core memory configuration.

**value1**: Assigned value for the specified `Option` (as described above).

## Notes

**SUBOPT** specifies options to be used with the Subspace eigensolver ( [[modopt|MODOPT]],SUBSP) during a modal analysis.

**Memory Allocation Option (** `Option` = MEMORY)

The Subspace eigensolver algorithm allocates two main pools of memory:

Memory for the internal subspace eigensolver iterations.

Memory for the specific subspace eigensolver working arrays.

The following table shows how memory is allocated for each option.

(table not available in the PyMAPDL source, see the Ansys help page)

The MIX1 configuration typically uses more memory than the MIX2 configuration, except when a large number of modes are requested for a small model.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SUBOPT.html
