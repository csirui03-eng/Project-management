---
apdl: "/COPY"
method: copy
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.files.Files.copy
generated: 2026-08-22
tags: [mapdl-command]
---

# /COPY

PyMAPDL: `mapdl.copy(fname1='', ext1='', fname2='', ext2='', distkey='', **kwargs)`

Copies a file.

## Parameters

**fname1**

File name to be copied and its directory path (248 characters maximum for both file name and directory). If you do not specify a directory path, it will default to your working directory and you can use all 248 characters for the file name.

The file name defaults to the current `Jobname`.

**ext1**: Filename extension (eight-character maximum).

**fname2**

File name to be created and its directory path (248 characters maximum for both file name and directory). If you do not specify a directory path, it will default to your working directory and you can use all 248 characters for the file name.

`Fname2` defaults to `Fname1`.

**ext2**: Filename extension (eight-character maximum). `Ext2` defaults to `Ext1`.

**distkey**

Key that specifies which copy operation is performed on all processes in distributed-memory parallel mode :

- `0 (OFF or NO)` - The program performs the copy operation only on the master process (default).
- `1 (ON or YES)` - The program performs the copy operation locally on each process.
- `2 or BOTH` - The program performs the copy operation for `Fname`. `Ext` on the master process and for `FnameN`. `Ext` on all processes.

## Notes

The original file is untouched. Ex: **/COPY**,A,,,B copies file A to B in the same directory. **/COPY**,A,DAT,,,INP copies the file `A.DAT` to `A.INP`. See the [Operations Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ope/Hlp_G_OPE8.html) for details. Mechanical APDL binary and ASCII files can be copied.

In distributed-memory parallel (DMP) mode, only the master process will copy `Fname1`. `Ext1` to `Fname2`. `Ext2` by default. However, when `DistKey` is set to 1 (or ON, or YES) or 2 (or BOTH), the command is executed by all processes. In this case, `Fname1` and `Fname2` will automatically have the process rank appended to them. This means `Fname1N`. `Ext1` will be copied to `Fname2N`. `Ext2` by all processes, where `N` is the DMP process rank. For more information see in the [Parallel Processing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_dan/HybParallel.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_COPY.html
