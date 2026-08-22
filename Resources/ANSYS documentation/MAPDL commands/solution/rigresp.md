---
apdl: "RIGRESP"
method: rigresp
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.rigresp
generated: 2026-08-22
tags: [mapdl-command]
---

# RIGRESP

PyMAPDL: `mapdl.rigresp(option='', method='', val1='', val2='', **kwargs)`

Specifies the rigid response calculation.

## Parameters

**option**

Flag to activate or deactivate the rigid response calculation:

- `1 (ON or YES)` - Activate.
- `2 (OFF or NO)` - Deactivate. This value is the default.

**method**

Method used to calculate the rigid response:

- `GUPTA` - Gupta method.
- `LINDLEY` - Lindley-Yow method.

**val1**

If `Method` = GUPTA, `Val1` represents the frequency F<sub>1</sub> in Hertz.

If `Method` = LINDLEY, `Val1` is the Zero Period Acceleration (ZPA). If a scale factor is defined (FACT in the [[svtyp|SVTYP]] command), it is used to scale this value

**val2**: If `Method` = GUPTA, `Val2` represents the frequency F<sub>2</sub> in Hertz.

## Notes

This rigid response calculation is only valid for single point response spectrum analysis ( [[spopt|SPOPT]], SPRS) and multiple point response spectrum analysis ( [[spopt|SPOPT]], MPRS) with combination methods ( [[srss|SRSS]] ), complete quadratic ( [[cqc|CQC]] ) or Rosenblueth ( [[rose|ROSE]] )

This command is also valid in PREP7.

- [Performing a Single-Point Response Spectrum (SPRS) Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR6_4.html#aYACegwrd)
- [Performing a Multi-Point Response Spectrum (MPRS) Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR6_10.html#spectrum_multipoint)
- [Rigid Responses](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc7.html#eqfa88cef4-37ad-4f72-9bc5-082358cc4a12) in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html)
- [[mmass|MMASS]] command

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RIGRESP.html
