---
apdl: "MAGOPT"
method: magopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.magopt
generated: 2026-08-22
tags: [mapdl-command]
---

# MAGOPT

PyMAPDL: `mapdl.magopt(value='', **kwargs)`

Specifies options for a 3D magnetostatic field analysis.

## Parameters

**value**

Option key:

- `0` - Calculate a complete H field solution in the entire domain using a single (reduced) potential.

  > [!WARNING]
  > When used in problems with both current sources and iron regions, errors may result due to numerical cancellation.

- `1` - Calculate and store a preliminary H field in "iron" regions (μ<sub>r</sub> ≠ 1). Requires flux-parallel boundary conditions to be specified on exterior iron boundaries. Used in conjunction with subsequent solutions with `VALUE` = 2 followed by `VALUE` = 3. Applicable to multiply- connected iron domain problems.

- `2` - Calculate and store a preliminary H field in "air" regions (μ<sub>r</sub> = 1). The air-iron interface is appropriately treated internally by the program. Used in conjunction with a subsequent solution with `VALUE` = 3. Applicable to singly-connected iron domain problems (with subsequent solution with `VALUE` = 3) or to multiply-connected iron domain problems (when preceded by a solution with `VALUE` = 1 and followed by a solution with `VALUE` = 3).

- `3` - Use the previously stored H field solution(s) and calculate the complete H field.

## Notes

Specifies the solution sequence options for a 3D magnetostatic field analysis using a scalar potential (MAG). The solution sequence is determined by the nature of the problem.

You cannot use constraint equations with `Value` = 1.

This command is also valid in PREP7.

Distributed-Memory Parallel (DMP) Restriction **MAGOPT**,3 is not supported in a DMP solution when the following contact elements are present in the model: `CONTA174`, `CONTA175`, or `CONTA177`.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MAGOPT.html
