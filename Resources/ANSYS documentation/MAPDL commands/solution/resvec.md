---
apdl: "RESVEC"
method: resvec
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.resvec
generated: 2026-08-22
tags: [mapdl-command]
---

# RESVEC

PyMAPDL: `mapdl.resvec(keyvect='', keyresp='', **kwargs)`

Calculates or includes residual vectors or residual responses

**Command default:** No residual quantities are calculated or included in the analysis.

## Parameters

**keyvect**

Residual vector key:

- `OFF` - Do not calculate or include residual vectors (default).
- `ON` - Calculate or include residual vectors.

**keyresp**

Residual response key:

- `OFF` - Do not calculate or include residual responses (default).
- `ON` - Calculate or include residual responses.

## Notes

In a [modal analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR_SMSUP.html), the **RESVEC** command calculates residual vectors (or responses). In a [mode-superposition transient](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR5_10.html#a4iQxq2c8mcm), [mode-superposition harmonic](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR4_MODESUPER.html#aMhQxq6emcm), PSD or [spectrum](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR6_2.html#) analysis, the command includes residual vectors. The command must be issued during the first modal solve.

In the expansion pass of a mode-superposition transient or mode-superposition harmonic analysis, the command includes residual responses.

In a component mode synthesis (CMS) [generation pass](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/advcmssuperelem.html#usingcms_elemcalc), the **RESVEC** command calculates one residual vector which is included in the normal modes basis used in the transformation matrix. It is supported for the three available [CMS methods](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc6.html#eq39b62ffb-3890-471d-a79e-2d6096214d0b). **RESVEC**,ON can only be specified in the first load step of a generation pass and is ignored if issued at another load step.

If rigid-body modes exist, pseudo-constraints are required for the calculation. Issue the [[d|D]],,,SUPPORT command to specify only the minimum number of pseudo-constraints necessary to prevent rigid-body motion.

Both residual vector and residual response approaches cannot be used in the same analysis.

For more information about residual vector or residual response formulation, see [Residual Vector Method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool9.html#resvec_125) [Residual Response Method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool9.html#thy_antools_resresp_eqn2)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RESVEC.html
