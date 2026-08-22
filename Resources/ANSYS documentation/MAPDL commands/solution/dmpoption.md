---
apdl: "DMPOPTION"
method: dmpoption
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.dmpoption
generated: 2026-08-22
tags: [mapdl-command]
---

# DMPOPTION

PyMAPDL: `mapdl.dmpoption(filetype='', combine='', rescombfreq='', deleopt='', **kwargs)`

Specifies distributed-memory parallel ( DMP ) file combination options.

**Command default:**

Local solution files are automatically combined into a single global file upon leaving the solution processor (for example, `JobnameN.RST` files are combined into one `Jobname.RST` file). This is true for all files except the `.Rnnn` files. Because they may be required in a subsequent analysis, local files are not automatically deleted after combination.

## Parameters

**filetype**

Type of solution file to combine after a distributed memory parallel solution. There is no default; if (blank), the command is ignored.

- `RST` - Results files ( `.RST`, `.RTH`, `.RMG`, `.RSTP` )
- `EMAT` - Element matrix files ( `.EMAT` ).
- `ESAV` - Element saved data files ( `.ESAV` )
- `MODE` - Modal results files ( `.MODE` )
- `MLV` - Modal load vector file ( `.MLV` )
- `IST` - Initial state file ( `.IST` )
- `FULL` - Full matrix file ( `.FULL` )
- `RFRQ` - Reduced complex displacement file ( `.RFRQ` )
- `RDSP` - Reduced displacement file ( `.RDSP` )
- `RNNN` - Multiframe restart files ( `.Rnnn` )

**combine**

Option to combine solution files.

- `Yes` - Combine solution files (default for all files except the `.Rnnn` files).
- `No` - Do not combine solution files (default for the `.Rnnn` files only).

**rescombfreq**

Frequency used to combine the local results files during a distributed memory parallel solution. This option applies only when `FileType` = RST and `Combine` = YES.

- `NONE` - Do not combine the local results files during solution. The local results files is combined only upon leaving the solution processor (default).
- `ALL` - Combines the local results files at every time point.
- `LAST` - Combines the local results files at the last time point of every load step.

**deleopt**

Option to delete local solution files of the type specified by `FileType` option after they are combined. This option applies only when `Combine` = Yes.

- `Yes` - Delete the local solution files after they are combined.
- `No` - Do not delete the local solution files after they are combined (default).

## Notes

The **DMPOPTION** command controls how solution files are written during a distributed-memory parallel ( DMP ) solution. This command is most useful for controlling how results files ( `.rst`, `.rth`, etc.) are written.

In a distributed memory parallel solution, a local results file is written by each process ( `JobnameN.ext`, where `N` is the process number). By default, the program automatically combines the local results files (for example, `JobnameN.rst` ) upon leaving the solution processor (for example, upon the [[finish|FINISH]] command) into a single global results file ( `Jobname.rst` ) which can be used in postprocessing.

Alternatively, the `ResCombFreq` argument can be used to combine the local results files at certain time points during the distributed solution to create a single combined results file that can be used to postprocess the model while the solution progresses. Doing so increases data communication and I/O between processes, leading to slower performance.

The `ResCombFreq` option only applies when solving static analyses, and harmonic or transient analyses that use the full method. It does not apply to mode superposition harmonic and mode superposition transient analyses. It does not apply when using the frequency domain decomposition option ( [[ddoption|DDOPTION]],FREQ) in a harmonic analysis.

To reduce communication and I/O, issue **DMPOPTION**,RST,NO to bypass this step of combining the local results files; the local files remain on the local disks in the current working directory. You can then use [[rescombine|RESCOMBINE]] in the POST1 general postprocessor ( [[post1|/POST1]] ) to read all results into the database for postprocessing.

The [[rescombine|RESCOMBINE]] command macro is intended for use with POST1. If you want to postprocess distributed parallel solution results using the POST26 time-history postprocessor ( [[post26|/POST26]] ), it is recommended that you combine your local results files into one global results file ( **DMPOPTION**,RST,YES or [[combine|COMBINE]] ).

Local `.emat`, `.esav`, `.mode`, `.mlv`, `.ist`, `.rfrq`, `.rdsp`, and `.full` files are also written (when applicable) by each process in a distributed memory parallel solution. If these files are not needed for a downstream solution or operation, you can issue the command **DMPOPTION**, `FileType`,NO for each file type to bypass the file combination step and thereby improve performance.

If **DMPOPTION**,MODE,NO or **DMPOPTION**,RST,NO is specified in a modal analysis, element results cannot be written to the combined mode file ( `Jobname.MODE` ). In this case, if distributed-memory parallel processing is used in a downstream harmonic or transient analysis that uses the mode-superposition method, the `MSUPkey` on the [[mxpand|MXPAND]] command can retain its value. However, if shared-memory parallel processing is used in the downstream harmonic or transient analysis, the `MSUPkey` is effectively set to NO.

If **DMPOPTION**,RNNN,YES is specified, all multiframe restart files named `Jobname.R001` to `Jobname.R999` are automatically combined upon leaving the solution processor (which can be slow and inefficient). To manually combine a single set of `.Rnnn` restart files, use the [[combine|COMBINE]] command.

Since local solution files may be required in a downstream analysis, the option to delete them after combination is disabled ( `DeleOpt` = No) by default. However, you can enable this option to reduce disk space usage by removing certain files if you know that they are not needed in any subsequent analysis.

**DMPOPTION** can be changed between load steps; however, doing so does not affect which set of solution files are combined. The values of `Combine` and `DeleOpt` are overwritten if **DMPOPTION** is issued multiple times for the same `FileType`. As a result, only the last values of `Combine` and `DeleOpt` for each `FileType` upon leaving the solution processor determine whether the local solution files are combined with or without deletion. For example, in a two-load-step solution, if **DMPOPTION**, RST, NO is issued in the first load step and **DMPOPTION**, RST, YES,,YES is issued in the second load step, all sets on the local results files will be combined, and then the local results files will be deleted. If the opposite is true ( **DMPOPTION**, RST, YES,,YES is issued in the first load step, and **DMPOPTION**, RST, NO is issued in the second load step), no results files are combined, and thus no local results files are deleted.

After using **DMPOPTION** to suppress file combination, you may find it necessary to combine the local files for a specific `FileType` for use in a subsequent analysis. In this case, use the [[combine|COMBINE]] command to combine local solution files into a single, global file.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DMPOPTION.html
