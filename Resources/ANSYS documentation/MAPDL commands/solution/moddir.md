---
apdl: "MODDIR"
method: moddir
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.moddir
generated: 2026-08-22
tags: [mapdl-command]
---

# MODDIR

PyMAPDL: `mapdl.moddir(key='', directory='', fname='', **kwargs)`

Enables remote read-only usage of modal analysis files or substructuring analysis files.

## Parameters

**key**

Key for enabling remote read-only usage of modal analysis files or [substructuring](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/advcms.html) analysis files:

- `1 (ON or YES)` - The program performs the analysis using remote files. The files are read-only.
- `0 (OFF or NO)` - The program performs the analysis using files located in the working directory (default).
- `LIST` - List remote modal files status, directory path, and file name.

**directory**

Directory path (248 characters maximum). The directory contains the modal analysis files or the substructuring generation pass files.

The directory path defaults to the current working directory.

**fname**

File name (no extension or directory path) for the modal analysis files or the substructuring generation pass files.

The file name defaults to the current `Jobname`.

## Notes

This commands is used when solving linked analyses in two different folders. It is mostly meant to be used to reduce solution time and disk space usage by specifying the path to required solution files rather than copying them in the Mechanical Application (see the file management sections of the following analyses: mode-superposition transient, mode-superposition harmonic, response spectrum, random vibration, and substructure generation in the Mechanical User's Guide ).

This command applies to the following analysis types:

- Spectrum ( [[antype|ANTYPE]],SPECTR)
- Modal restart ( [[antype|ANTYPE]], MODAL, RESTART)
- Mode-superposition transient ( [[antype|ANTYPE]],TRANS and [[trnopt|TRNOPT]], MSUP)
- Mode-superposition harmonic ( [[antype|ANTYPE]],HARM and [[hropt|HROPT]], MSUP)
- Substructuring ( [[antype|ANTYPE]],SUBSTR).

Using the default for both the directory path ( `Directory` ) and the file name ( `Fname` ) is not valid. At least one of these values must be specified.

In a spectrum analysis and in mode-superposition analyses, **MODDIR** must be issued during the first solution and at the beginning of the solution phase (before [[lvscale|LVSCALE]] in particular). In a spectrum analysis, remote modal files usage is not supported when mode file reuse is activated ( `modeReuseKey` = YES on [[spopt|SPOPT]] ).

After a [PSD spectrum analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR6_8.html#aiiQxq1b2mcm), **MODDIR** can be issued in POST26 prior to the [[store|STORE]] command.

In a modal restart analysis, **MODDIR** must be issued during the first solution. Remote modal files usage cannot be activated in a modal restart analysis if during the first modal analysis:

- Enforced static modes have been calculated ( `EnforcedKey` = ON on [[modcont|MODCONT]] ).
- Element result superposition key ( `MSUPkey` on [[mxpand|MXPAND]] ) was set to NO, whereas it is set to YES in the modal restart.

When using distributed-memory parallel processing, if element results calculation based on element modal results is activated for the spectrum analysis ( `Elcalc` = YES on [[spopt|SPOPT]] ), **MODDIR** usage can significantly reduce computation time as it decreases the size of the distributed `.rst` files to be combined at the end of spectrum analysis solution.

In a substructuring or CMS analysis, **MODDIR** can be issued during either of the following analysis phases:

- The first solution of the first restart of a generation pass. `ExpMth` on [[seopt|SEOPT]] must be set to MODDIR during the first solve of the primary generation pass.
- The first solution of the expansion pass.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MODDIR.html
