---
apdl: "TRNOPT"
method: trnopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.trnopt
generated: 2026-08-22
tags: [mapdl-command]
---

# TRNOPT

PyMAPDL: `mapdl.trnopt(method='', maxmode='', initialacc='', minmode='', mcfwrite='', tintopt='', vaout='', dmpsfreq='', engcalc='', mckey='', **kwargs)`

Specifies transient analysis options.

## Parameters

**method**

Solution method for the transient analysis:

- `FULL` - Full method (default).
- `MSUP` - Mode-superposition method.

**maxmode**: Largest mode number to be used to calculate the response (for `Method` = MSUP). Defaults to the highest mode calculated in the preceding modal analysis.

**initialacc**

Key to activate calculation of initial acceleration:

- `(blank)` - Initial accelerations are not calculated (default).
- `INIL` - Calculate initial acceleration for a full transient analysis using the lumped mass matrix.

**minmode**: Smallest mode number to be used (for `Method` = MSUP). Defaults to 1.

**mcfwrite**

Modal coordinates output key to the `Jobname.mcf` file (valid only for the mode-superposition method). To control how `Jobname.mcf` is written, specify options on the [[mcfopt|MCFOPT]] command.

- `NO` - Modal coordinates are not written to `Jobnamemcf`.
- `YES` - Modal coordinates are written to the text file `Jobname.mcf` (default).

**tintopt**

[Time integration method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_anproc2.html#anpsolu) for the transient analysis:

- `NMK or 0` - Newmark algorithm (default).
- `HHT or 1` - HHT algorithm (valid only for the full transient method).

**vaout**

Velocities and accelerations output key (valid only for [mode-superposition transient analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR5_10.html#a4iQxq2c8mcm) ):

- `NO` - No output of velocities and accelerations (default).
- `YES` - Write velocities and accelerations to the reduced displacement file, `Jobnamerdsp`.

**dmpsfreq**: Average excitation frequency (Hz) for the calculation of equivalent viscous damping from structural damping input ( [[dmpstr|DMPSTR]] and [[mp|MP]],DMPS). See [Damping](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR1D.html#strelemdamp) `DMPSFreqTab` on [[dmpstr|DMPSTR]] ), it supersedes this value.

**engcalc**

Additional element energies calculation key:

- `NO` - Do not calculate additional element energies (default).
- `YES` - Calculate damping energy and work done by external loads.

**mckey**

Modal coordinates output key to the `.rdsp` file (valid only for the mode-superposition method):

- `AUTO` - Writing depends on the modal analysis settings of the [[mxpand|MXPAND]] command (default).
- `YES` - Always write the modal coordinates to the file `Jobname.rdsp`. A subsequent expansion pass ( [[expass|EXPASS]] ) is not supported.

## Notes

Specifies transient analysis ( [[antype|ANTYPE]],TRANS) options. If used in SOLUTION, this command is valid only within the first load step. Use the [[tintp|TINTP]] command to set transient integration parameters.

To include [residual vectors](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR_SMSUP.html#ans_str_moda_resresp) in your [mode-superposition transient](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR5_10.html#a4iQxq2c8mcm) analysis ( `Method` = MSUP), specify [[resvec|RESVEC]],ON.

For `Method` = MSUP, `MAXMODE` and `MINMODE` are ignored after a modal restart analysis where remote modal files usage ( [[moddir|MODDIR]] ) and residual vector calculation ( [[resvec|RESVEC]],ON) have been activated.

`Method` = MSUP is not available for ocean loading.

By default in a mode-superposition transient analysis, reaction force and other force output contains only static contributions. If you want to postprocess the velocities, accelerations, and derived results ( `Lab` = TOTAL, DAMP, or INERT on the [[force|FORCE]] command), set `VAout` = YES to activate velocity and acceleration output.

The calculation of additional energies ( `EngCalc` = YES) is valid only for the full solution method ( `Method` = FULL). The `Jobname.ESAV` file is always saved in this case. The numerical integration for damping energy and work are consistent only if solution data are written to the database for every substep ( [[outres|OUTRES]],ALL,ALL, [[outres|OUTRES]],ESOL,ALL, or [[outres|OUTRES]],VENG, ALL). For more information, see [Damping Energy](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool16.html#) [Work Done by External Loads](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool16.html#)

This command is also valid in PREP7.

Additional product restrictions for the **TRNOPT** command are shown in the table below.

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TRNOPT.html
