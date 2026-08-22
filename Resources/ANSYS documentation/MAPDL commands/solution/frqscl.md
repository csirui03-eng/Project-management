---
apdl: "FRQSCL"
method: frqscl
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.frqscl
generated: 2026-08-22
tags: [mapdl-command]
---

# FRQSCL

PyMAPDL: `mapdl.frqscl(scaling='', **kwargs)`

Turns on automatic scaling of the entire mass matrix and frequency range for modal analyses.

**Command default:** Mechanical APDL uses automatic scaling if appropriate.

## Parameters

**scaling**

- `Off` - Do not use automatic scaling of the mass matrix and frequency range.
- `On` - Use automatic scaling of the mass matrix and frequency range.

## Notes

This command is available only for modal analyses using the Block Lanczos, PCG Lanczos, Supernode, Subspace, or Unsymmetric mode extraction method ( [[modopt|MODOPT]],LANB, LANPCG, SNODE, SUBPS, or UNSYM).

Use this command to deactivate or force activation of automatic scaling of the entire mass matrix and frequency range for modal analyses where the entire mass matrix is significantly different (that is, orders of magnitude different) than the entire stiffness matrix (for example, due to the particular unit system being used). Where the mass matrix is significantly smaller compared to the stiffness matrix, the eigenvalues will tend to approach very large numbers (\>10e12), making the selected mode-extraction method less efficient and more likely to miss modes.

You can force the entire mass matrix and frequency range to be scaled via **FRQSCL**,ON. Doing so brings the stiffness and mass matrices closer together in terms of orders of magnitude, improving efficiency and reducing the likelihood of missed modes. The resulting eigenvalues are then automatically scaled back to the original system. If you are using micro MKS units, where the density is typically very small compared to the stiffness, you may want to force scaling on.

If the stiffness and mass are on the same scale, **FRQSCL**,ON has no effect.

This command is not valid and has no effect when used with [[msave|MSAVE]],ON in a modal analysis with the PCG Lanczos mode extraction method.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FRQSCL.html
