---
apdl: "OUTPR"
method: outpr
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.outpr
generated: 2026-08-22
tags: [mapdl-command]
---

# OUTPR

PyMAPDL: `mapdl.outpr(item='', freq='', cname='', **kwargs)`

Controls the solution printout.

## Parameters

**item**

Item for print control:

- `BASIC` - Basic quantities (nodal DOF solution, nodal reaction loads, and element solution) (default).
- `NSOL` - Nodal DOF solution.
- `RSOL` - Nodal reaction loads.
- `ESOL` - Element solution.
- `NLOAD` - Element nodal loads. When [nonlinear stabilization](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRUNST.html#) is active, the stabilization force/moments are also printed.
- `SFOR` - Stabilization force/moment at the applicable nodes (valid only when [nonlinear stabilization](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRUNST.html#) is active).
- `VENG` - Element energies. When [nonlinear stabilization](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRUNST.html#) is active, the energy dissipation due to stabilization is also printed.
- `RSFO` - Result section force/moment output (valid only when a [result section](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_resultsec.html#) is defined). Result section output is always written to a file named `JobnameSECF`.
- `V` - Nodal velocity (applicable to structural transient analysis only ( [[antype|ANTYPE]],TRANS)).
- `A` - Nodal acceleration (applicable to structural transient analysis only ( [[antype|ANTYPE]],TRANS)).
- `ALL` - All of the above solution items.

**freq**: Print solution for this item every `Freq` <sup>th</sup> (and the last) substep of each load step. If - `n`, print up to `n` equally spaced solutions (only applies to static or full transient analyses when automatic time stepping is enabled). If NONE, suppress all printout for this item for this load step. If ALL, print solution for this item for every substep. If LAST, print solution for this item only for the last substep of each load step. For a modal analysis, use NONE or ALL.

**cname**

Name of the component, created with the [[cm|CM]] command, defining the selected set of nodes or elements for which this specification is active. If blank, the set is all entities.

The component named must be of the same type as the item, i.e. nodal or element. A component name is not allowed with the BASIC, RSFO, or ALL labels.

## Notes

Controls the solution items to be printed, the frequency with which they are printed (in static, transient, or full harmonic analyses), and the set of nodes or elements to which this specification applies (in static, transient, or full harmonic analyses). An item is associated with either a node ( [[nsol|NSOL]], [[rforce|RFORCE]], V, and A items) or an element (all of the remaining items). The specifications are processed in the order that they are input. Use **OUTPR**,STAT to list the current specifications and use **OUTPR**,ERASE to erase all the current specifications.

In addition to **OUTPR**, [[outres|OUTRES]] and [[outgeom|OUTGEOM]] also control solution output. You can issue up to 50 of these output-control commands (any combination of the three) in an analysis.

As described above, **OUTPR** writes some or all items (depending on analysis type) for all elements. To restrict the solution printout, use **OUTPR** to selectively suppress ( `Freq` = NONE) the writing of solution data, or first suppress the writing of all solution data ( **OUTPR**,ALL,NONE) and then selectively turn on the writing of solution data with subsequent **OUTPR** commands.

If the generalized plane strain feature is active and **OUTPR** is issued, the change of fiber length at the ending point during deformation and the rotation of the ending plane about X and Y during deformation will be printed if any displacement at the nodes is printed. The reaction forces at the ending point will be printed if any reaction force at the nodes is printed.

Nodal reaction loads ( `Item` = RSOL) are processed according to the specifications listed for the [[prrsol|PRRSOL]] command.

Result printouts for interactive sessions are suppressed for models with more than 10 elements except when the printout is redirected to a file using the [[output|/OUTPUT]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_OUTPR.html
