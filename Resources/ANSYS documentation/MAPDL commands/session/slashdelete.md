---
apdl: "/DELETE"
method: slashdelete
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.files.Files.slashdelete
generated: 2026-08-22
tags: [mapdl-command]
---

# /DELETE

PyMAPDL: `mapdl.slashdelete(fname='', ext='', distkey='', **kwargs)`

Deletes a file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to the current `Jobname`.

**ext**: Filename extension (eight-character maximum).

**distkey**

Key that specifies which file deletion action is performed on all processes in distributed-memory parallel mode:

- `0 (OFF or NO)` - The program performs the file deletion only on the master process (default).
- `1 (ON or YES)` - The program performs the file deletion locally on each process.
- `2 or BOTH` - The program performs file deletion for `Fname`. `Ext` on the master process and for `FnameN`. `Ext` on all processes.

## Notes

In distributed-memory parallel (DMP) mode, only the master process will delete `Fname`. `Ext` by default. However, when `DistKey` is set to 1 (or ON, or YES) or 2 (or BOTH), the command is executed by all processes. In this case, `Fname` will automatically have the process rank appended to it. This means `FnameN`. `Ext` will be deleted by all processes, where `N` is the DMP process rank. For more information see in the [Parallel Processing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_dan/HybParallel.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DELETE_sl.html
