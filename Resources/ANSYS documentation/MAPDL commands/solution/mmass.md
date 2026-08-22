---
apdl: "MMASS"
method: mmass
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.mmass
generated: 2026-08-22
tags: [mapdl-command]
---

# MMASS

PyMAPDL: `mapdl.mmass(option='', zpa='', **kwargs)`

Specifies the missing mass response calculation.

## Parameters

**option**

Flag to activate or deactivate missing mass response calculation.

- `0 (OFF or NO)` - Deactivate (default).
- `1 (ON or YES)` - Activate.

**zpa**: Zero Period Acceleration Value. If a scale factor FACT is defined on the [[svtyp|SVTYP]] command, it is applied to this value.

## Notes

The missing mass calculation is valid only for single point excitation response spectrum analysis ( [[spopt|SPOPT]], SPRS) and for multiple point response spectrum analysis ( [[spopt|SPOPT]], MPRS) performed with base excitation using acceleration response spectrum loading. Missing mass is supported in a spectrum analysis only when the preceding modal analysis is performed with the Block Lanczos, PCG Lanczos, Supernode, or Subspace eigensolver (Method =LANB, LANPCG, SNODE, or SUBSP on the [[modopt|MODOPT]] command).

The velocity solution is not available ( `Label` = VELO on the combination command: [[srss|SRSS]], [[cqc|CQC]]...) when the missing mass calculation is activated.

The missing mass calculation is not supported when the spectrum analysis is based on a linear perturbation modal analysis performed after a nonlinear base analysis.

The missing mass is not supported when superelements are present.

To take into account the contribution of the truncated modes, the residual vector ( [[resvec|RESVEC]] ) can be used in place of the missing mass response. This is of particular interest if the velocity solution is requested or if a nonlinear prestress is included in the analysis (linear perturbation), or if a superelement is present, since the missing mass cannot be used in these cases.

In a multiple point response spectrum analysis ( [[spopt|SPOPT]],MPRS), the **MMASS** command must precede the participation factor calculation command ( [[pfact|PFACT]] ).

This command is also valid in PREP7.

- [Performing a Single-Point Response Spectrum (SPRS) Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR6_4.html#aYACegwrd)
- [Performing a Multi-Point Response Spectrum (MPRS) Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR6_10.html#spectrum_multipoint)
- [Missing-Mass Response](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc7.html#eq7fe0e910-baf8-4b0e-8a3e-67dc4190f121)
- [[rigresp|RIGRESP]] command

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MMASS.html
