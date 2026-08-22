---
apdl: "DAMPOPT"
method: dampopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.dampopt
generated: 2026-08-22
tags: [mapdl-command]
---

# DAMPOPT

PyMAPDL: `mapdl.dampopt(option='', value='', **kwargs)`

Sets damped eigensolver options.

**Command default:**

By default, the shift strategy is not activated for the damped eigensolver. This ensures a faster solve process but limits the number of eigenvalues that can be found.

The default memory allocation strategy is used. Mechanical APDL evaluates the resources of the machine to choose the in-core or out-of-core mode.

## Parameters

**option**

Damped eigensolver option:

- `SHIFT` - Activate or deactivate the shift strategy of the damped eigensolver to move to a frequency range of interest. The `FREQB` value of the [[modopt|MODOPT]] command is used to choose the first frequency shift (see notes for details).

  Valid input for `Value` when `Option` = SHIFT:

  - `OFF` - Do not activate the shift strategy.
  - `ON` - Activate the shift strategy (default).

- `MEMORY` - Controls the memory allocation strategy for the Damped eigensolver.

  Valid input for `Value` when `Option` = MEMORY:

  - `DEFAULT` - Default memory configuration (default). Everything is determined dynamically with respect to current machine resources.
  - `INCORE` - Fully in-core memory configuration.
  - `MIX1` - First level of mixed in-core / out-of-core configuration.
  - `MIX2` - Second level of mixed in-core / out-of-core configuration.
  - `OUTOFCORE` - Fully out-of-core memory configuration.

**value**: Assigned value for the specified `Option` (as described above).

## Notes

**DAMPOPT** specifies options to be used with the damped eigensolver ( [[modopt|MODOPT]],DAMP) during a modal analysis ( [[antype|ANTYPE]],MODAL).

Activating the shift strategy ( `Option` = SHIFT and `Value` = ON) enables the eigensolver to find higher frequency eigenvalues that might otherwise be missed. The SHIFT option has two objectives:

- Extract high frequency eigenvalues according to the `FREQB` argument specified with [[modopt|MODOPT]].
- Unlock an auto-shift feature, so the algorithm will chain several analyses automatically then aggregate the solutions in one single results set.

If `FREQE` is specified on [[modopt|MODOPT]], the specified value is used to filter the complex eigenfrequencies based on magnitude.

When the shift strategy is activated ( **DAMPOPT**,SHIFT,ON)

- and `FREQB` on [[modopt|MODOPT]] is specified, the damped eigensolver only produces eigenfrequencies with a real part greater than `FREQB`
- and `FREQB` on [[modopt|MODOPT]] is not specified, the damped eigensolver finds eigenvalues closest to the 0 Hz point.

**Memory Allocation Option (** `Option` = MEMORY)

The damped eigensolver algorithm allocates two main pools of memory:

Memory for the internal damped eigensolver iterations.

Memory for the specific damped eigensolver working arrays.

The following table shows how memory is allocated for each option.

(table not available in the PyMAPDL source, see the Ansys help page)

The MIX1 configuration typically uses more memory than the MIX2 configuration, except when a large number of modes are requested for a small model.

**Example Usage**

[Example: Shift Option Usage on DAMPOPT](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR3_15.html#str_modal_dampExFig2)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DAMPOPT.html
