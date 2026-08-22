---
apdl: "SEOPT"
method: seopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.seopt
generated: 2026-08-22
tags: [mapdl-command]
---

# SEOPT

PyMAPDL: `mapdl.seopt(sename='', sematr='', sepr='', sesst='', expmth='', seoclvl='', lpnamekey='', **kwargs)`

Specifies substructure analysis options.

## Parameters

**sename**: The name (case-sensitive, 32-character maximum) assigned to the `.sub` superelement matrix file. This field defaults to `Fname` on the [[filname|/FILNAME]] command.

**sematr**

Matrix generation key:

- `1` - Generate stiffness (or conductivity) matrix (default).
- `2` - Generate stiffness and mass (or conductivity and specific heat) matrices.
- `3` - Generate stiffness, mass and damping matrices.

**sepr**

Print key:

- `0` - Do not print superelement matrices or load vectors.
- `1` - Print both load vectors and superelement matrices.
- `2` - Print load vectors but not matrices.

**sesst**

Stress-stiffening key:

- `0` - Do not save space for stress stiffening in a later run.
- `1` - Save space for the stress stiffening matrix (calculated in a subsequent generation run after the expansion pass).

**expmth**

Expansion method for expansion pass:

- `BACKSUB` - Save necessary factorized matrix files (for example, the `.LN22` file) for backsubstitution during the subsequent expansion passes (default). This normally results in a large usage of disk space.
- `MODDIR` - This is the same expansion method as BACKSUB, except that the static correction vectors (see the first term of in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html)) are stored on the `.bclv` file instead of the `.LN22` file. This option is required when remote read-only file usage is used during the first solution of the first restart of a generation pass (see the [[moddir|MODDIR]] command).
- `RESOLVE` - Do not save factorized matrix files. Global stiffness matrix will be reformed during expansion pass. This option provides an effective way to save disk space usage. This option cannot be used if the use pass uses large deflections ( [[nlgeom|NLGEOM]],ON).
- `NONE` - Do not save factorized matrix files. With this option, the expansion pass is not possible when factorized matrix files are required.
- `BCLV` - Do not save factorized matrix files. The static correction vectors (see the first term of ) are stored in the `.bclv` file. With this option, the expansion pass is not possible when factorized matrix files are required.

**seoclvl**

For the added-mass calculation, the ocean level to use when ocean waves ( [[octype|OCTYPE]],,WAVE) are present:

- `ATP` - The ocean level at this point in time (default).
- `MSL` - The mean ocean level.

**lpnamekey**

- `ON` - All files created during the generation pass are named using `Sename`.
- `OFF` - All files created during the generation pass are named using the `Jobname` defined for the analysis (see [[filname|/FILNAME]] command) except for the `.sub` file, which uses `Sename` if specified (default).

## Notes

**SEOPT** specifies substructure analysis options ( [[antype|ANTYPE]],SUBSTR). If used during solution, the command is valid only within the first load step.

When ocean waves ( [[octype|OCTYPE]],,WAVE) are present, the `SeOcLvL` argument specifies the ocean height or level to use for the added-mass calculation, as the use-run analysis type is unknown during the generation run.

The expansion pass method RESOLVE is not supported with component mode synthesis analysis ( [[cmsopt|CMSOPT]] ). `ExpMth` is automatically set to BACKSUB for CMS analysis. The RESOLVE method invalidates the use of the [[numexp|NUMEXP]] command. The RESOLVE method does not allow the restarting of the substructure generation pass and the computation of results based on nodal velocity and nodal acceleration (damping force, inertial force, kinetic energy, etc.) in the substructure expansion pass.

If `ExpMth` = NONE or BCLV in a substructure analysis or component mode synthesis (CMS) analysis ( [[cmsopt|CMSOPT]] ) using the fixed-interface ( [[cmsopt|CMSOPT]],FIX) or free-interface ( [[cmsopt|CMSOPT]] ,FREE) methods, you cannot restart the generation pass or perform the expansion pass. (In CMS analyses using those methods, however, the expansion pass is possible when element-results calculation is activated in the generation pass ( `ELCALC` = YES on [[cmsopt|CMSOPT]] )). The `ExpMth` argument is not required for CMS analysis using the residual-flexible free-interface method ( [[cmsopt|CMSOPT]],RFFB).

For linear perturbation substructure generation pass with multiple substructures, set `LPnameKey` = ON to avoid copying files at the end of each generation pass with the [[copy|/COPY]] command. For an example with CMS analysis using the fixed-interface method, see.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SEOPT.html
