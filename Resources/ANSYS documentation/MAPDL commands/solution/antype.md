---
apdl: "ANTYPE"
method: antype
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.antype
generated: 2026-08-22
tags: [mapdl-command]
---

# ANTYPE

PyMAPDL: `mapdl.antype(antype='', status='', ldstep='', substep='', action='', prelp='', **kwargs)`

Specifies the analysis type and restart status.

**Command default:**

New static analysis.

## Parameters

**antype**

Analysis type (defaults to the previously specified analysis type, or to STATIC if none specified):

- `STATIC or 0` - Perform a static analysis. Valid for all degrees of freedom.
- `BUCKLE or 1` - Perform a buckling analysis. Implies that a previous static solution was performed with prestress effects calculated ( [[pstres|PSTRES]],ON). Valid for structural degrees of freedom only.
- `MODAL or 2` - Perform a modal analysis. Valid for structural and fluid degrees of freedom.
- `HARMIC or 3` - Perform a harmonic analysis. Valid for structural, fluid, magnetic, and electrical degrees of freedom.
- `TRANS or 4` - Perform a transient analysis. Valid for all degrees of freedom.
- `SUBSTR or 7` - Perform a substructure analysis. Valid for all degrees of freedom.
- `SPECTR or 8` - Perform a spectrum analysis. Implies that a previous modal analysis was performed. Valid for structural degrees of freedom only.
- `SOIL or 9` - Perform a soil analysis including geostatic stress equilibrium or consolidation. Valid for structural and fluid-pore-pressure degrees of freedom.

**status**

Specifies the status of the analysis (new or restart):

- `NEW` - Specifies a new analysis (default). If NEW, the remaining fields on this command are ignored.

- `RESTART` - Specifies a restart of a previous analysis. Valid for static, modal, and transient (full or mode- superposition method) analyses. For more information about restarting static and transient analyses, see [Multiframe Restart](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS3_12.html#BASmultprocmap52199) [Modal Analysis Restart](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS3_12.html#modalrestex)

  Multiframe restart is also valid for harmonic analysis, but is limited to 2D magnetic analysis only.

  A substructure analysis (backsubstitution method only) can be restarted for the purpose of generating additional load vectors. For more information, see the [[seopt|SEOPT]] command and [Applying Loads and Creating the Superelement Matrices](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/aKa7uq1a9ldm.html#substr_usingsubstr_appload)

**ldstep**

Specifies the load step at which a multiframe restart begins.

For full transient and nonlinear static analyses, the default is the highest load step number found in the `Jobname.Rnnn` files for the current jobname in the current directory.

For mode-superposition transient analyses, the default is none.

**substep**

Specifies the substep at which a multiframe restart begins.

For full transient and nonlinear static analyses, the default is the highest substep number found for the specified `LDSTEP` in the `Jobname.Rnnn` files in the current directory.

For mode-superposition transient analyses, the default is none.

**action**

Specifies the manner of a multiframe restart.

- `CONTINUE` - The program continues the analysis based on the specified `LDSTEP` and `SUBSTEP` (default). The current load step is continued. If the end of the load step is encountered in the `.Rnnn` file, a new load step is started. The program deletes all `.Rnnn` files, or `.Mnnn` files for mode-superposition transient analyses, beyond the point of restart and updates the `.LDHI` file if a new load step is encountered.

- `ENDSTEP` - At restart, force the specified load step ( `LDSTEP` ) to end at the specified substep ( `SUBSTEP` ), even though the end of the current load step has not been reached. At the end of the specified substep, all loadings are scaled to the level of the current ending and stored in the `.LDHI` file. A run following this ENDSTEP starts a new load step. This capability allows you to change the load level in the middle of a load step. The program updates the `.LDHI` file and deletes all `.Rnnn` files, or `.Mnnn` files for mode- superposition transient analyses, beyond the point of ENDSTEP. The `.Rnnn` or `.Mnnn` file at the point of ENDSTEP are rewritten to record the rescaled load level.

- `RSTCREATE` - At restart, retrieve information to be written to the results file for the specified load step ( `LDSTEP` ) and substep ( `SUBSTEP` ). Be sure to use [[outres|OUTRES]] to write the results to the results file. This action does not affect the `.LDHI` or `.Rnnn` files. Previous items stored in the results file at and beyond the point of RSTCREATE are deleted. This option cannot be used to restart a mode-superposition transient analysis.

- `PERTURB` - At restart, a linear perturbation analysis (static, modal, buckling, or full harmonic) is performed for the specified load step ( `LDSTEP` ) and substep ( `SUBSTEP` ). This action does not affect the `.LDHI`, `.Rnnn`, or `.RST` files.

  For a [linear perturbation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strlinpertother.html) analysis, set `Action` = PERTURB; otherwise, the existing restart files, such as the `.LDHI`, `.Rnnn`, or `.RST` file, may be modified by the linear perturbation analysis. Issue the [[perturb|PERTURB]] command to indicate the desired analysis type (STATIC, MODAL, BUCKLE, HARMONIC, or SUBSTR ).

**prelp**

Flag indicating whether a subsequent linear perturbation will be performed:

- `YES` - Specifies the first static analysis with a sequential linear perturbation analysis. Setting PRELP = YES is necessary for acoustics-structural interaction linear perturbation analysis, if the [[morph|MORPH]] command with `StrOpt` = YES is not issued.
- `NO` - No specification for a subsequent linear perturbation (default).

## Notes

If using the **ANTYPE** command to change the analysis type in the same SOLVE session, the program issues the following message: "Some analysis options have been reset to their defaults. Please verify current settings or respecify as required." Typically, the program resets commands such as [[nlgeom|NLGEOM]] and [[eqslv|EQSLV]] to their default values.

If you want to read in view factors after restarting a radiation analysis, issue VFOPT,READ after ANTYPE,,REST.

The analysis type ( `Antype` ) cannot be changed if a restart is specified. Always save parameters before doing a restart. For more information on the different types of restart, see [Restarting an Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS3_12.html#bassolumodres)

This command is also valid in PREP7.

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANTYPE.html
