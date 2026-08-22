---
apdl: "RESCONTROL"
method: rescontrol
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.rescontrol
generated: 2026-08-22
tags: [mapdl-command]
---

# RESCONTROL

PyMAPDL: `mapdl.rescontrol(action='', ldstep='', frequency='', maxfiles='', maxtotalfiles='', filetype='', **kwargs)`

Controls file writing for multiframe restarts.

## Parameters

**action**

Command action:

- `DEFINE` - Specifies how often `.xnnn` restart files (default) or `.rdnn` remeshing database files (for [nonlinear mesh adaptivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnaexample.html) analysis) are written for a load step. The file type controlled by this command is determined by `Filetype`.

- `FILE_SUMMARY` - Prints the substep and load-step information for all `.xnnn` or `.rdnn` files for the current jobname in the current directory. If specified, all other arguments are ignored.

- `STATUS` - Issuing the command lists the current status in the tables of restart controls specified previously by **RESCONTROL**. If this option is specified, all other arguments are ignored.

- `NORESTART` - Cleans up some of the restart files after a distributed-memory parallel (DMP) solution. (Not valid for [nonlinear mesh adaptivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnaexample.html).)

  The master process will not have the following files in the working directory at the end of the run: `.esav`, `.osav`, `.xnnn`, `.rdb`, `.ldhi`. The worker processes will not have the following files in the working directory at the end of the run: `.esav`, `.osav`, `.xnnn`, `.rst` (or `.rth`, etc.). Some restart files are never written, some are removed upon exiting the solution processor (for example, upon [[finish|FINISH]] ), and some are removed upon exiting the program.

  This option is useful for cleaning up files written by all distributed processes, especially when you know that these restart files will not be needed later. If this option is specified, all other arguments are ignored.

  If this option is used in a shared-memory parallel (SMP) environment, most restart files in the working directory are removed. It has the same effect as issuing **RESCONTROL**,,NONE.

- `LINEAR` - Same as `Action` = DEFINE, but for linear static applications only. For a linear static analysis, the restart capability is normally not needed; however, it is typically needed when a subsequent linear perturbation analysis is desired. By default, none of the restart files are written for a linear static analysis.

- `DELETE` - Delete the restart control specification corresponding to the `Ldstep` label on a previous **RESCONTROL**,DEFINE command.

**ldstep**

Specifies how the `.xnnn` or `.rdnn` files are written for the specified load steps. This option also affects how often the load history information is written to the `.ldhi` file.

- `ALL` - Write the `.xnnn` or `.rdnn` files at the same substep `Frequency` for all load steps; write the load history information to the `.ldhi` file for all load steps. For `.rdnn` files, this option is the default.

- `LAST` - Write the `.xnnn` or `.rdnn` files for the last load step only; write load- history information to the `.ldhi` file for the last load step only. This option is the default for nonlinear static and full transient analyses for `.xnnn` files. If specified, all remaining arguments are ignored.

- `N` - Number that indicates how often the `.xnnn` or `.rdnn` files are written.

  Input a positive number to write the `.xnnn` or `.rdnn` files at the substep `Frequency` indicated only for load step `N`. Other load steps will be written at the default substep frequency or at a frequency defined by a previous **RESCONTROL** specification. Load- history information is written to the `.ldhi` file only for load steps `N`.

  Specifying a negative number (- `N` ) is valid for controlling `.xnnn` files only. The files are written for every `N` th load step at the specified substep `Frequency`. The load history information is written to the `.ldhi` file every `N` th load step. This option is suitable for restart applications in which more than a few hundred load steps are required. Compared to the ALL and positive `N` options, it can save disk space, as the `.ldhi` file is smaller and fewer `.xnnn` files are written.

  If `Ldstep` = - `N`, all other `Ldstep` options specified by **RESCONTROL** are ignored and the program follows the - `N` option (write load history information every `N` th load step). If you want to change this pattern, issue **RESCONTROL**,DELETE, - `N`, then issue another **RESCONTROL** command with the desired `Ldstep` option.

- `NONE` - No multiframe restart files ( `.rdb`, `.ldhi`, `.xnnn` ) are created. (Not valid for [nonlinear mesh adaptivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnaexample.html) analysis.)

  This option is the default for mode-superposition analyses. The remaining arguments are ignored.

  For nonlinear static, linear static, and full transient analyses, this option enables a restart to occur at the last or abort point (using the `.emat`, `.esav` or `.osav`, and `.db` files).

  For mode-superposition transient analyses, this option allows a restart from the last point using the `.rdsp` and `.db` files.

**frequency**

Frequency at which the `.xnnn` files are written at the substep level, or at which the `.rdnn` files are written at the remeshing level:

- `NONE` - Do not write `.xnnn` files for this load step (not available for `.rdnn` files).

- `LAST` - Write the `.xnnn` files for the last substep of the load step only (default for nonlinear static and full transient analyses), or write the `.rdnn` files for the last remesh of the load step only (default for [nonlinear mesh adaptivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnaexample.html) analysis).

- `N` - If `N` is positive, write the `.xnnn` files at every `N` th substep of a load step, or write the `.rdnn` files at every `N` th remesh of a load step.

  If `N` is negative (not valid for `.rdnn` files), write `N` equally spaced `.xnnn` files within a load step.

  In nonlinear static and full transient analyses, `-N` is valid only when automatic time stepping is enabled ( [[autots|AUTOTS]],ON).

  In mode-superposition analyses, negative `N` is always valid.

**maxfiles**

Maximum number of `.xnnn` files to save within a load step ( not available for `.rdnn` files):

- `-1` - Overwrite existing `.xnnn` files (default). The total maximum number of `.xnnn` files for one run is 999. If this number is reached before the analysis is complete, the program will reset the `.xnnn` file numbering back to 1 and continue to write `.xnnn` files; the program keeps the newest 999 restart files and overwrites the oldest restart files. For this option, the maximum number of files can be changed to a number less than 999 by setting the MAXTotalFiles argument.
- `0` - Do not overwrite any existing `.xnnn` files. The total maximum number of `.xnnn` files for one run is 999. If this number is reached before the analysis is complete, the analysis continues but no longer writes any `.xnnn` files.
- `N` - Maximum number of `.xnnn` files to keep for each load step. When `N` `.xnnn` files have been written for a load step, the program overwrites the first `.xnnn` file of that load step for subsequent substeps. `N` must be \<= 999. If a total of 999 restart files is reached before the analysis is complete, the analysis continues but writes no additional `.xnnn` files.

**maxtotalfiles**

Total number of restart files to keep. Default = 999 for `.xnnn` files and 99 for `.rdnn` files. This option is valid only when `MAXFILES` = -1 (default).

Valid `MAXTotalFiles` values are 1 through 999 for `.xnnn` files, and 1 through 99 for `.rdnn` files.

When the total number of restart files written exceeds `MAXTotalFiles`, the program resets the `.xnnn` or `.rdnn` file numbering back to 1 and continues to write `.xnnn` or `.rdnn` files. The newest files are retained and the oldest files are overwritten.

The `MAXtotalFiles` value specified applies to all subsequent load steps. To reset it to the default, reissue the command with `MAXTotalFiles` = 0 or some negative value.

If `MAXTotalFiles` is set to different values at different load steps, and if the value of `MAXTotalFiles` specified in the prior load step is larger than that of the current load step, the program can only overwrite the current number of maximum restart files up to the number `MAXTotalFiles` currently specified (which is smaller than the previous number).

The recommended way to control the maximum number of restart files is to specify `MAXTotalFiles` at the first load step and not vary it in subsequent load steps. Also, `MAXTotalFiles` is best used when `Ldstep` = - `N` or ALL.

**filetype**

The type of restart file to be controlled by this command. Valid only when `Action` = DEFINE:

- `XNNN` - Control `.xnnn` files (default).
- `RDNN` - Control `.rdnn` remeshing database files. Needed only for a [nonlinear mesh adaptivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnaexample.html) analysis.

## Notes

**RESCONTROL** sets up the restart parameters for a multiframe restart, enabling you to restart an analysis from any load step and substep for which there is an `.xnnn` file. You can perform a multiframe restart for static and transient (full or mode-superposition method) analyses only. For more information about multiframe restarts and descriptions of the contents of the files used, see [Restarting an Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS3_12.html#bassolumodres)

**Syntax**

- Multiframe restart files are generically indicated here as `.xnnn` files. They correspond to `.rnnn` files for nonlinear static and full transient analyses, and `.mnnn` files for mode-superposition analyses.
- Remeshing database files are indicated as `.rdnn` files. This type of restart file is needed only after remeshing during a [nonlinear mesh adaptivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnaexample.html) analysis.
- When `Action` = DEFINE, the specified `Filetype` determines the type of file ( `.xnnn` or `.rdnn` ) controlled by this command.

**Number of Restart Files Allowed**

- The total number of restart files for any analysis cannot exceed 999 (for example, `jobname.r001` to `jobname.r999` ).
- The total number of remeshing database files cannot exceed 99 (for example, `jobname.rd01` to `jobname.rd99` ).

**Considerations for** [Nonlinear Mesh Adaptivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnaexample.html) Analysis

- To control both `.xnnn` and `.rdnn` file writing ( `Filetype` = XNNN and `Filetype` = RDNN, respectively), separate **RESCONTROL** commands are necessary.
- `Action` = NORESTART and `Ldstep` = NONE are not valid and will cause the analysis to fail.
- `Ldstep` = `-N` is not valid for controlling `.xnnn` files.

**Limiting the Number of Files Saved**

- If you have many substeps for each load step and are writing `.xnnn` files frequently, you may want to set `MAXFILES` to limit the number of `.xnnn` files saved, as they can fill your disk quickly.
- You can specify `MAXFILES` and `Frequency` for individual load steps. These arguments take on the default value or the value defined by **RESCONTROL**,,ALL, `Frequency`, `MAXFILES` if they are not explicitly defined for a specific load step.
- When `.xnnn` files are written over many load steps, you may want to further limit the number of `.xnnn` files by setting `MAXTotalFiles`.

**Maximum Number of Load Steps**

- You can specify a maximum of ten load steps; that is, you can issue the **RESCONTROL**,,N command a maximum of ten times. Specified load steps cannot be changed in a restart.

**Specifying** `Ldstep` = LAST or `-N`

- The program accepts only one occurrence of **RESCONTROL** with `Ldstep` = LAST. If you issue **RESCONTROL**,,LAST, `Frequency`, `MAXFILES` multiple times, the last specification overwrites the previous one.
- The program accepts only one occurrence of **RESCONTROL** with a negative `Ldstep` value ( **RESCONTROL**, `N` where `N` is a negative number). If you issue **RESCONTROL** multiple times with a negative `Ldstep` value, the last specification overwrites the previous one.

**Using** **RESCONTROL** in a Restarted Analysis

- The **RESCONTROL** command is not valid in the restarted load step of a restart analysis. It is only valid in subsequent load steps.

**Example Usage**

- [Multiframe Restart](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS3_12.html#bassolumodres)
- [Linear Perturbation Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strlinpertinputs.html#linpert2genpass)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RESCONTROL.html
