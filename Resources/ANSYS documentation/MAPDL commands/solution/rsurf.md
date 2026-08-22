---
apdl: "RSURF"
method: rsurf
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.radiosity.Radiosity.rsurf
generated: 2026-08-22
tags: [mapdl-command]
---

# RSURF

PyMAPDL: `mapdl.rsurf(options='', delopts='', etnum='', **kwargs)`

Generates the radiosity surface elements and stores them in the database.

## Parameters

**options**

Command options:

- `CLEAR` - Deletes radiosity surface elements and nodes. The set of elements and nodes to be deleted is defined by `Delopts`. `ETNUM` is ignored.
- `DEFINE` - Creates the radiosity surface elements and nodes (default).
- `STAT` - Shows the status/listing. Other command options are ignored.

**delopts**

Deletion options

- `ALL` - Deletes all radiosity surface elements and nodes.
- `LAST` - Deletes radiosity surface elements and nodes created by the last **RSURF** command.

**etnum**: Element type number. Leave blank to indicate the next available number.

## Notes

This command generates the radiosity surface elements ( `SURF251`, `SURF252` ) based on the [[rsymm|RSYMM]] and [[rdec|RDEC]] parameters and stores them in the database. It works only on the faces of selected underlying elements that have RDSF flags on them and all corner nodes selected. You can issue multiple **RSURF** commands to build the radiosity model. However, all **RSURF** commands must be issued after issuing the [[rsymm|RSYMM]] command, and after the model is complete (that is, after all meshing operations are complete).

If you do issue multiple **RSURF** commands for different regions, you must first mesh the different regions, and then generate the radiosity surface elements on each meshed region individually. Use **RSURF**,,,ETNUM to assign a separate element type number to each region. This procedure allow you to identify the individual regions later in the multi-field analysis.

If the underlying solid elements are higher order, the radiosity surface elements are always lower order (4- or 3-node in 3D or 2-node in 2D). Decimation will always occur before any symmetry operations.

For 2D axisymmetric YR models, the newly-generated nodes can have only positive Y coordinates.

The **RSURF** command assigns real constant set number 1 to all `SURF251` and `SURF252` elements generated, irrespective of the current real constant set attribute pointer ( [[real|REAL]] command). If the generated elements require a real constant set other than number 1, you must manually change the set number for those elements by using the [[emodif|EMODIF]],,REAL command.

If you have already issued **RSURF** for a surface and you issue **RSURF** again, the program creates a new set of radiosity surface elements and nodes over the existing set, resulting in an erroneous solution. Distributed-Memory Parallel (DMP) Restriction This command is not supported in a DMP solution.

This is an action command (that creates or deletes surface meshes) and is serial in nature. Even if a DMP solution is running, the **RSURF** command runs serially.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RSURF.html
