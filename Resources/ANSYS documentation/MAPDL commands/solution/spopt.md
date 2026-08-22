---
apdl: "SPOPT"
method: spopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.spopt
generated: 2026-08-22
tags: [mapdl-command]
---

# SPOPT

PyMAPDL: `mapdl.spopt(spectype='', nmode='', elcalc='', modereusekey='', **kwargs)`

Selects the spectrum type and other spectrum options.

## Parameters

**spectype**

Spectrum type:

- `SPRS` - Single point excitation response spectrum (default). See also [[svtyp|SVTYP]].
- `MPRS` - Multiple point excitation response spectrum.
- `DDAM` - Dynamic design analysis method.
- `PSD` - Power spectral density.

**nmode**: Use the first `NMODE` modes from the modal analysis. Defaults to all extracted modes, as specified by the [[modopt|MODOPT]] and [[bucopt|BUCOPT]] commands. `NMODE` cannot be larger than 10000.

**elcalc**

Element results calculation key:

- `NO` - Do not calculate element results and reaction forces (default).
- `YES` - Calculate element results and reaction forces, as well as the nodal degree of freedom solution.

**modereusekey**

Key for existing `MODE` file reuse when running multiple spectrum analyses:

- `NO` - No spectrum analysis has been performed yet (default).
- `YES` - This is not the first spectrum analysis. The `MODE` file will be reused and the necessary files will be cleaned up for the new spectrum analysis.

## Notes

Valid only for a spectrum analysis ( [[antype|ANTYPE]],SPECTR). This operation must be preceded by a modal solution ( [[antype|ANTYPE]],MODAL) with the appropriate files available. Both the spectrum analysis and the preceding modal analysis must be performed under the same Mechanical APDL version number.

If used in SOLUTION, this command is valid only within the first load step.

Element results are calculated ( `Elcalc` = YES) only if the element modal results are available (written to the `Jobname.mode` file with `MSUPkey` = YES on the [[mxpand|MXPAND]] command). For `Sptype` = SPRS, MPRS, and DDAM, if the element results calculation is activated ( `Elcalc` = YES) and element modal results are not available, it is deactivated automatically.

For SPRS, DDAM or MPRS analyses, modal responses can be combined and stored directly in the `Jobname.rst` file during spectrum solution according to the mode combination method command issued ( [[srss|SRSS]], [[cqc|CQC]], etc.) for `Elcalc` = YES. This can save significant time compared to the method for `Elcalc` = NO, which requires generating the file of POST1 commands ( `Jobname.mcom` file) to be read in POST1 to do the mode combinations. For details and example usage, see [Spectrum Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR6_10.html), and Example: Multi-Point Response Spectrum (MPRS) Analysis.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPOPT.html
