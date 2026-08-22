---
apdl: "MXPAND"
method: mxpand
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.mxpand
generated: 2026-08-22
tags: [mapdl-command]
---

# MXPAND

PyMAPDL: `mapdl.mxpand(nmode='', freqb='', freqe='', elcalc='', signif='', msupkey='', modeselmethod='', engcalc='', **kwargs)`

Specifies modal or buckling analysis expansion options.

## Parameters

**nmode**: Number of modes or array name (enclosed in percent signs) to expand and write. If blank or ALL, expand and write all modes within the frequency range specified. If -1, do not expand and do not write modes to the results file during the analysis. If an array name is input, the array must contain 1 for the expanded modes and zero otherwise, where the array index corresponds to the mode number. To specify an array containing the individual modes to expand, enclose the array name in percent (%) signs (for example, **MXPAND**,%arrname%). Use the [[dim|*DIM]] command to define the array.

**freqb**: Beginning, or lower end, of frequency range of interest. If `FREQB` and `FREQE` are both blank, expand and write the number of modes specified without regard to the frequency range. Defaults to the entire range.

**freqe**: Ending, or upper end, of frequency range of interest.

**elcalc**

Element calculation key:

- `NO` - Do not calculate element results, reaction forces, and energies (default).
- `YES` - Calculate element results, reaction forces, energies, and the nodal degree of freedom solution.

**signif**

Expand only those modes whose significance level exceeds the `SIGNIF` threshold (only applicable when `ModeSelMethod` is defined).

If `ModeSelMethod` = MODC, the significance level of a mode is defined as the mode coefficient divided by the maximum mode coefficient of all modes.

If `ModeSelMethod` = EFFM, the significance level of a mode is defined as the modal effective mass, divided by the total mass.

If `ModeSelMethod` = DDAM, the significance level of a mode is defined as the modal effective weight, divided by the total weight.

Any mode whose significance level is less than `SIGNIF` is considered insignificant and is not expanded. The higher the `SIGNIF` threshold, the fewer the number of modes expanded. `SIGNIF` defaults to 0.001, except for the case of DDAM mode selection method where it defaults to 0.01. If `SIGNIF` is specified as 0.0, it is taken as 0.0.

**msupkey**

Element result superposition key:

- `NO` - Do not write element results to the mode file `Jobnamemode`.
- `YES` - Write element result to the mode file for use in the expansion pass of a subsequent mode- superposition PSD, spectrum, transient, or harmonic analysis. This value is the default if all of the following conditions exist:
  - `Elcalc` = YES.
  - The mode shapes are normalized to the mass matrix.
  - `FREQB` and `FREQE` are blank or 0.0.
  - No superelement is defined.

**modeselmethod**

Methods for mode selection (not supported for complex eigensolvers):

- `` - No mode selection is performed (default).
- `EFFM` - The mode selection is based on the modal effective masses.
- `MODC` - The mode selection is based on the mode coefficients.
- `DDAM` - The mode selection is based on DDAM procedure (see [Mode Selection Based on the DDAM Method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR_SMSUP.html#)

**engcalc**

Additional element energies calculation key:

- `NO` - Do not calculate additional energies (default).
- `YES` - Calculate average, amplitude, and peak values for the following: stiffness and kinetic energies, and damping energy.

## Notes

Specifies the number of modes to expand and write over a frequency range for a modal ( [[antype|ANTYPE]] ,MODAL) or buckling ( [[antype|ANTYPE]],BUCKLE) analysis. If used in SOLUTION, this command is valid only within the first load step.

There is no limit on the number of expanded modes ( `NMODE` ). However, there is a limit on the maximum number of modes used via the [[get|*GET]], MODE command, mode combinations, and the [[mdamp|MDAMP]] command.

With `MSUPkey` = YES, the computed element results ( `Elcalc` = YES) are written to `Jobname.mode` for use in subsequent downstream mode-superposition analyses, including harmonic, transient, and all spectrum analyses. This significantly reduces computation time for the combination or expansion passes. For limitations and available elemental results, see.

The calculation of additional energies ( `EngCalc` = YES) is valid only for `Method` = DAMP on the [[modopt|MODOPT]] command and `Method` = QRDAMP with `Cpxmod` = CPLX on the [[modopt|MODOPT]] command.

If a mode selection method ( `ModeSelMethod` ) is defined, only the selected modes will be expanded. See [Using Mode Selection](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR_SMSUP.html#strModSelBasDD)

For array input ( `NMODE` ), the array must be dimensioned to be the size of the number of modes extracted ( `NMODE` on the [[modopt|MODOPT]] command). A value of 1 in the array indicates the mode is to be expanded, and a value of 0 indicates not to expand the mode. For the DAMP modal solution, the modes are in pairs, so be sure to verify that both modes of a pair have the same value. (For example, if modes \#3 and \#4 are a pair, indices 3 and 4 in the array should have the same value, 0 or 1.)

For [linear perturbation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strlinpertother.html) modal analyses, you must set both `Elcalc` and `MSUPkey` to YES so that the downstream stress expansion pass can produce a solution consistent with the linear or nonlinear base (static or full transient) analysis. The prestressed nonlinear element history (saved variables) is accessible only in the first and second phases of the linear perturbation. The downstream mode superposition analysis (such as MSUP or PSD) can only reuse the nonlinear information contained in the `Jobname.mode` file that is generated in the linear perturbation.

In a distributed-memory parallel (DMP) analysis, you must issue **MXPAND** to specify the number of modes to expand when computing the modes and mode shapes. In a DMP run, **MXPAND** cannot be issued in an expansion pass ( [[expass|EXPASS]] ).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MXPAND.html
