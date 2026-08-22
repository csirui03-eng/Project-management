---
apdl: "CBDOF"
method: cbdof
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.cbdof
generated: 2026-08-22
tags: [mapdl-command]
---

# CBDOF

PyMAPDL: `mapdl.cbdof(fname1='', ext1='', fname2='', ext2='', kpos='', clab='', kshs='', tolout='', tolhgt='', tolthk='', **kwargs)`

Activates cut-boundary interpolation (for submodeling).

## Parameters

**fname1**

File name and directory path (248 characters maximum, including directory) from which to read boundary node data. If no specified directory path exists, the path defaults to your working directory and you can use all 248 characters for the file name.

The file name defaults to `Jobname`.

**ext1**: Filename extension (eight-character maximum). The extension defaults to NODE if `Fname1` is blank.

**fname2**

File name and directory path (248 characters maximum, including directory) to which cut-boundary **D** commands are written. If no specified directory path exists, the path defaults to your working directory and you can use all 248 characters for the file name.

The file name defaults to `Jobname`.

**ext2**: Filename extension (eight-character maximum). The extension defaults to CBDO if `Fname2` is blank.

**kpos**

Position on `Fname2` to write block of [[d|D]] commands:

- `0` - Beginning of file (overwrite existing file).
- `1` - End of file (append to existing file).

**clab**: Label (eight characters maximum, including the colon) for this block of [[d|D]] commands on `Fname2`. his label is appended to the colon (:). Defaults to CB `n`, where `n` is the cumulative iteration number for the data set currently in the database. For imaginary data (see KIMG on the [[starset|*SET]] command), `Clab` defaults to CI `n`.

**kshs**

Shell-to-solid submodeling key:

- `0` - Solid-to-solid or shell-to-shell submodel.
- `1` - Shell-to-solid submodel.

**tolout**: Extrapolation tolerance about elements, based on a fraction of the element dimension. Submodel nodes outside the element by more than `TOLOUT` are not accepted as candidates for DOF extrapolation. Defaults to 0.5 (50 percent).

**tolhgt**: Height tolerance above or below shell elements, in units of length. Used only for shell-to-shell submodeling ( `KSHS` = 0). Submodel nodes off the element surface by more than `TOLHGT` are not accepted as candidates for degree-of-freedom interpolation or extrapolation. Defaults to 0.0001 times the maximum element dimension.

**tolthk**: Height tolerance above or below shell elements, based on a fraction of the shell element thickness. Used only for shell-to-solid submodeling (KSHS = 1). Submodel nodes off the element surface by more than `TOLTHK` are not accepted as candidates for DOF interpolation or extrapolation. Defaults to 0.1 times the average shell thickness.

## Notes

File `Fname1` should contain a node list for which boundary conditions are to be interpolated ( [[nwrite|NWRITE]] ). File `Fname2` is created to contain interpolated boundary conditions written as a block of [[d|D]] commands.

Boundary conditions are written for the active degree-of-freedom set for the element from which interpolation is performed. Interpolation occurs on the selected set of elements. The block of [[d|D]] commands begins with an identifying colon label and ends with a `/EOF` command. The colon label is of the form : `Clab` (described above).

Interpolation from multiple results sets can be performed by looping through the results file in a user-defined macro. Additional blocks can be appended to `Fname2` by using `KPOS` and unique colon labels. To read the block of commands, issue the [[input|/INPUT]] command with the appropriate colon label.

If the model has coincident (or very close) nodes, the **CBDOF** must be applied to each part of the model separately to ensure that the mapping of the nodes is correct. For example, if nodes belonging to two adjacent parts linked by springs are coincident, the operation should be performed on each part of the model separately.

Resume the coarse model database at the beginning of the cut-boundary procedure. The database should have been saved after the first coarse model solution, as the number of nodes in the database and the results file must match, and internal nodes are sometimes created during the solution.

This command cannot be used to interpolate the magnetic edge-flux (AZ) degree of freedom.

> [!WARNING]
> Relaxing the `TOLHGT` or `TOLTHK` tolerances to allow submodel nodes to be “found” can produce poor submodel results.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CBDOF.html
