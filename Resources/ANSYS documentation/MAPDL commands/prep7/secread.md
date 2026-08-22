---
apdl: "SECREAD"
method: secread
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.secread
generated: 2026-08-22
tags: [mapdl-command]
---

# SECREAD

PyMAPDL: `mapdl.secread(fname='', ext='', option='', **kwargs)`

Reads a custom section library or a user-defined section mesh into Mechanical APDL.

## Parameters

**fname**

Section library file name and directory path containing the section library file (248 characters maximum, including directory). If you do not specify a directory path, it will default to your working directory and you can use all 248 characters for the file name.

When the **SECREAD** command is given without a directory path, the command searches for a section library in the following order:

- The user's home directory
- The current working directory
- The path specified by the [[seclib|/SECLIB]] command

The file name defaults to `Jobname` if `Fname` is left blank.

**ext**: Filename extension (eight-character maximum). The extension defaults to SECT if `Ext` is left blank.

**option**

- `LIBRARY` - Reads in a library of sections and their associated section data values; the default. A section library may be created by editing the section-defining portions of the `Jobname.LOG` file and saving it with a `.SECT` suffix.
- `MESH` - Reads in a user mesh section file containing the cell connectivity, cell flags, and nodal coordinates for the current beam section of subtype MESH as defined by [[sectype|SECTYPE]]. See the [Notes](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SECREAD.html#SECREAD.extranote1) section of this command description for details about user mesh section files. [[secwrite|SECWRITE]] builds mesh files based on 2D models you create.

## Notes

The **SECREAD** command operates on the section specified via the most recently issued **SECTYPE** command. Issue a separate **SECREAD** command for each section ID that you want to read in.

Here are excerpts from a sample user section mesh file for a section with 75 nodes, 13 cells, and 9 nodes per cell for a two-hole box section. Illustrations of the two-hole box section and the cell mesh for it appear later in this command description.

(table not available in the PyMAPDL source, see the Ansys help page)

The mesh file is divided into three sections: the First Line, the Cells Section, and the Nodes Section. Here are brief descriptions of the contents of each.

**First Line:** The First Line defines the number of nodes and the number of cells for the mesh.

**Cells Section:** The Cells Section contains as many lines as there are cells. In this example, there are thirteen cells, so there are thirteen lines in this section. In each line, the number "1" that follows the cell connectivity information is the material number.

Cell nodal connectivity must be given in a counterclockwise direction, with the center node being the ninth node. For details, see .

**Nodes Section:** The Nodes Section contains as many lines as there are nodes. In this example, there are 75 nodes, so there are a total of 75 lines in this section. Each node line contains the node's boundary flag, the Y coordinate of the node, and the Z coordinate of the node. Currently, all node boundary flags appear as 0s in a cell mesh file (as illustrated in ). Since all node boundary flags are 0, **SECREAD** ignores them when it reads a cell mesh file into Mechanical APDL.

There cannot be any gaps in the node numbering of a cell mesh. The nodes in a cell mesh must be numbered consecutively, with the first node having a node number of 1, and the last node having a node number that is equal to the maximum number of nodes in the cell mesh.

(figure omitted: Two-hole Box Section, see the Ansys help page)

(figure omitted: Cell Mesh for the Two-hole Box Section, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SECREAD.html
