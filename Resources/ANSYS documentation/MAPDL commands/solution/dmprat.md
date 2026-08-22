---
apdl: "DMPRAT"
method: dmprat
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.dmprat
generated: 2026-08-22
tags: [mapdl-command]
---

# DMPRAT

PyMAPDL: `mapdl.dmprat(ratio='', **kwargs)`

Sets a modal damping ratio.

**Command default:**

Use damping as defined by [Damping](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR1D.html#strelemdamp)

## Parameters

**ratio**: Modal damping ratio (for example, 2% is input as 0.02).

## Notes

Sets a damping ratio for use in a mode-superposition transient analysis ( [[antype|ANTYPE]],TRANS with [[trnopt|TRNOPT]],MSUP), a mode-superposition harmonic analysis ( [[antype|ANTYPE]],HARMIC with [[hropt|HROPT]],MSUP) analysis, or a spectrum ( [[antype|ANTYPE]],SPECTR) analysis.

**DMPRAT** can also be defined in a substructure analysis that uses component mode synthesis. The damping ratio is added on the diagonal of the reduced damping matrix, as explained in [Component Mode Synthesis (CMS)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc6.html#eq39b62ffb-3890-471d-a79e-2d6096214d0b)

This command is also valid in PREP7.

**Additional Information**

[Damping Matrices](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool3.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DMPRAT.html
