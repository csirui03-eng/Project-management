---
apdl: "UPCOORD"
method: upcoord
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.upcoord
generated: 2026-08-22
tags: [mapdl-command]
---

# UPCOORD

PyMAPDL: `mapdl.upcoord(factor='', key='', **kwargs)`

Modifies the coordinates of the active set of nodes, based on the current displacements.

## Parameters

**factor**: Scale factor for displacements being added to nodal coordinates. If `FACTOR` = 1.0, the full displacement value will be added to each node, 0.5, half the displacement value will be added, etc. If `FACTOR` = -1, the full displacement value will be subtracted from each node, etc.

**key**

Key for zeroing displacements in the database:

- `OFF` - Do not zero the displacements (default).
- `ON` - Zero the displacements.

## Notes

The **UPCOORD** command uses displacements stored in the Mechanical APDL database, and not those contained within the results file, `Jobname.RST`. Nodal coordinates are updated each time the command is issued. After updating, both the nodal displacements and rotations are set to zero if `Key` = ON.

For structural solutions with an updated mesh, unless the coefficient matrix is otherwise reformed (for example, a new analysis or [[nlgeom|NLGEOM]],ON) it should first be reformed by issuing a [[kuse|KUSE]],-1 command.

**UPCOORD** should not be issued between load steps in structural analysis.

For a multiphysics simulation where a CFD or electromagnetic field is being coupled to a structure undergoing large displacements, all (or a portion) of the surrounding field mesh may take part in the structural solution to "move" with the displacing structure. You can use the **UPCOORD** command with a suitable `FACTOR` to update the coordinates of the nodes using the newly computed displacements. The mesh will now conform with the displaced structure for subsequent field solutions. However, the mesh should always be restored to its original location by using an **UPCOORD**, `FACTOR` command before performing any subsequent structural solutions. This is true for both repeated linear solutions, and for nonlinear restarts. (All saved displacements are relative to the original mesh location.)

> [!WARNING]
> Orientation nodes for beams and pipes always have zero displacements. Therefore, although this command may alter the locations of other beam and pipe nodes, it has no effect on orientation nodes. Carefully inspect the element coordinate systems on the updated model.

This command is not intended to replace either the large-displacement or birth-and-death capability.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_UPCOORD.html
