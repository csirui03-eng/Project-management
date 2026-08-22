---
apdl: "BFINT"
method: bfint
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.bfint
generated: 2026-08-22
tags: [mapdl-command]
---

# BFINT

PyMAPDL: `mapdl.bfint(fname1='', ext1='', fname2='', ext2='', kpos='', clab='', kshs='', tolout='', tolhgt='', **kwargs)`

Activates the body force interpolation operation.

## Parameters

**fname1**

File name and directory path (248 characters maximum, including directory) from which to read data for interpolation. If you do not specify a directory path, it will default to your working directory and you can use all 248 characters for the file name.

The file name defaults to `Jobname`.

**ext1**: Filename extension (eight-character maximum). The extension defaults to NODE if `Fname1` is blank.

**fname2**

File name and directory path (248 characters maximum, including directory) to which **BF** commands are written. If you do not specify a directory path, it will default to your working directory and you can use all 248 characters for the file name.

The file name defaults to `Jobname`.

**ext2**: Filename extension (eight-character maximum). The extension defaults to BFIN if `Fname2` is blank.

**kpos**

Position on `Fname2` to write block of **BF** commands:

- `0` - Beginning of file (overwrite existing file).
- `1` - End of file (append to existing file).

**clab**: Label (8 characters maximum, including the colon) for this block of **BF** commands in `Fname2`. This label is appended to the colon (:). Defaults to BF `n`, where `n` is the cumulative iteration number for the data set currently in the database.

**kshs**

Shell-to-solid submodeling key:

- `0` - Solid-to-solid or shell-to-shell submodel.
- `1` - Shell-to-solid submodel.

**tolout**: Extrapolation tolerance about elements, based on a fraction of the element dimension. Submodel nodes outside the element by more than `TOLOUT` are not accepted as candidates for DOF extrapolation. Defaults to 0.5 (50%).

**tolhgt**

Height tolerance above or below shell elements, in units of length. Used only for shell-to-shell submodeling ( `KSHS` = 0). Submodel nodes off the element surface by more than `TOLHGT` are not accepted as candidates for DOF interpolation or extrapolation. Defaults to 0.0001 times the maximum element dimension.

> [!WARNING]
> Relaxing this tolerance to allow submodel nodes to be found may cause poor submodel results.

## Notes

File `Fname1` should contain a node list for which body forces are to be interpolated ( [[nwrite|NWRITE]] ). File `Fname2` is created, and contains interpolated body forces written as a block of nodal [[bf|BF]] commands.

Body forces are interpolated from elements having TEMP as a valid body force or degree of freedom, and only the label TEMP is written on the nodal [[bf|BF]] commands. Interpolation is performed for all nodes on file `Fname1` using the results data currently in the database. For layered elements, use the [[layer|LAYER]] command to select the locations of the temperatures to be used for interpolation. Default locations are the bottom of the bottom layer and the top of the top layer.

The block of [[bf|BF]] commands begins with an identifying colon label command and ends with a `/EOF` command. The colon label command has the form : `Clab`. Interpolation from multiple results sets can be performed by looping through the results file in a user-defined macro. Additional blocks can be appended to `Fname2` by using `KPOS` and unique colon labels. Issue [[input|/INPUT]], with the appropriate colon label, to read the block of commands.

If the model has coincident (or very close) nodes, **BFINT** must be applied to each part of the model separately to ensure that the mapping of the nodes is correct. For example, if nodes belonging to two adjacent parts linked by springs are coincident, the operation should be performed on each part of the model separately.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFINT.html
