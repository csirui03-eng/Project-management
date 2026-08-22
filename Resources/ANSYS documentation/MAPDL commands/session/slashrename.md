---
apdl: "/RENAME"
method: slashrename
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.files.Files.slashrename
generated: 2026-08-22
tags: [mapdl-command]
---

# /RENAME

PyMAPDL: `mapdl.slashrename(fname1='', ext1='', fname2='', ext2='', distkey='', **kwargs)`

Renames a file.

## Parameters

**fname1**

The file to be renamed. You can also include an optional directory path as part of the specified file name; if not, the default file location is the working directory.

File name defaults to the current `Jobname`.

**ext1**: Filename extension (eight-character maximum).

**fname2**

The new name for the file. You can also include an optional directory path as part of the new file name; if not, the default is the working directory. A maximum of 248 characters is allowed for the file name (or combined file name and directory path, if both are specified).

`Fname2` defaults to `Fname1`.

**ext2**: Filename extension (eight-character maximum). `Ext2` defaults to `Ext1`.

**distkey**

Key that specifies which rename operation is performed on all processes in distributed-memory parallel mode:

- `0 (OFF or NO)` - The program performs the rename operation only on the master process (default).
- `1 (ON or YES)` - The program performs the rename operation locally on each process.
- `2 or BOTH` - The program performs the rename operation for `Fname`. `Ext` on the master process and for `FnameN`. `Ext` on all processes.

## Notes

Renames a file. Ex: **/RENAME**,A,,,B renames file A to B in the same directory. **/RENAME**,A,DAT,,,INP renames file A.DAT to A.INP. On all systems, this command will overwrite any existing file named B. See the [Operations Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ope/Hlp_G_OPE8.html) for details. Only Mechanical APDL binary files should be renamed. Use [[sys|/SYS]] and system renaming commands for other files.

In distributed-memory parallel (DMP) mode, only the master process will rename `Fname1`. `Ext1` to `Fname2`. `Ext2` by default. However, when `DistKey` is set to 1 (or ON, or YES) or 2 (or BOTH), the command is executed by all processes. In this case, `Fname1` and `Fname2` will automatically have the process rank appended to them. This means `Fname1N`. `Ext1` will be renamed to `Fname2N`. `Ext2` by all processes, where `N` is the DMP process rank. For more information see in the [Parallel Processing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_dan/HybParallel.html).

Renaming across system partitions may be internally done by a copy and delete operation on some systems.

This command is valid only at the Begin level.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RENAME.html
