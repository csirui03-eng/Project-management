---
apdl: "PRMC"
method: prmc
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.prmc
generated: 2026-08-22
tags: [mapdl-command]
---

# PRMC

PyMAPDL: `mapdl.prmc(lstep='', sbstep='', timfrq='', kimg='', hibeg='', hiend='', matrix='', **kwargs)`

Prints the modal coordinates from a mode-superposition solution.

## Parameters

**lstep**, **sbstep**: Print the solution identified as load step `LSTEP` and substep `SBSTEP`.

**timfrq**: As an alternative to `LSTEP` and `SBSTEP`, print the solution at the time value `TIMFRQ` (for [[antype|ANTYPE]],TRANS) or frequency value `TIMFRQ` (for [[antype|ANTYPE]],HARMIC). `LSTEP` and `SBSTEP` should be left blank.

**kimg**

Key for printing real or imaginary solution. Valid only for [[antype|ANTYPE]],HARMIC.

- `0 (or blank)` - Print the real solution (default).
- `1` - Print the imaginary solution.
- `2` - Print the amplitude.

**hibeg**, **hiend**: For cyclic symmetry solutions, print the solutions in the harmonic index solution range `HIbeg` to `HIend`. Defaults to all harmonic indices (all modes).

**matrix**: Create an APDL Math dense matrix with the name entered on this field (up to 32 characters; for nomenclature guidelines see [Guidelines for Parameter Names](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/Hlp_P_APDL3_2.html#apdlhidparmtlm8599) `Matrix` = blank), no APDL Math matrix is created.

## Notes

**PRMC** prints the modal coordinates (the factors which modes may be multiplied by to obtain their contribution to the response) at a certain time point (transient analyses) or frequency point (harmonic analyses).

The printout contains four columns: the mode number (labelled MODE), the modal frequency (labelled FREQ), the modal coordinate or mode multiplier (labelled MULT), and the normalized modal coordinate (labelled NORM). The normalized modal coordinate is the ratio of absolute value of the mode multiplier divided by the sum of the absolute values of all multipliers listed (at a solution time/frequency and harmonic index). It may be useful for identifying the dominant modes. Maximum values of each column are also listed at the end of each report.

By default, the real part of the modal coordinate values are printed even if the modal coordinates are complex.

When `Matrix` is specified, an APDL Math dense matrix similar to the one created with the [[dmat|*DMAT]] command is created. If **PRMC** is issued multiple times with the same name entered on `Matrix` or if a matrix with the specified name already exists, the matrix is overwritten. This matrix contains four to five columns depending on the analysis. The first four columns are the ones printed by **PRMC**. The fifth column contains the harmonic index for cyclic analysis only. This matrix can then be used in APDL Math data processing and file handling (See [APDL Math](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdlmathex.html) [[export|*EXPORT]] can be issued to export the **PRMC** data to a `.csv` file.

For transient analyses, a `.rdsp` None file must be available. For harmonic analyses, a `.rfrq` None file must be available. The content of these files depends on the [[outres|OUTRES]] command settings. Note that the default for mode-superposition transient analysis is to write the reduced displacement file every 4th substep. For more information, see Command Default in the [[outres|OUTRES]] command description.

For a cyclic harmonic mode-superposition analysis, use the [[cycfiles|CYCFILES]] command to identify the `.rfrq` None and modal `.rst` None files. For other analyses, use the [[file|FILE]] command to specify the `.rdsp` or `.rfrq` file.

This information can also be obtained from the optional `Jobname.mcf` text file (see the [[trnopt|TRNOPT]] and [[hropt|HROPT]] commands), and it can be plotted using the [[plmc|PLMC]] command. For more information on modal coordinates, see [Mode-Superposition Method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool9.html#thy_antools_resresp) in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html)

**Example Usage**

``` apdl
/POST1
```

FILE,,rdsp ! Specify Jobname.rdsp file from a previous MSUP transient analysis ! Print modal coordinates from the second loadstep and fourth substep PRMC,2,4,,,,,MAT ! also create an APDL Math matrix called MAT \*EXPORT,MAT,CSV,PRMCFILE.CSV ! Export MAT to a.csv file

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRMC.html
