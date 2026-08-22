---
apdl: "/PBC"
method: pbc
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.pbc
generated: 2026-08-22
tags: [mapdl-command]
---

# /PBC

PyMAPDL: `mapdl.pbc(item='', key='', min_='', max_='', abs_='', **kwargs)`

Shows boundary condition (BC) symbols and values on displays.

**Command default:**

No symbols displayed.

## Parameters

**item**

Label identifying the item:

- `U` - Applied translational constraints (UX, UY, UZ).
- `ROT` - Applied rotational constraints (ROTX, ROTY, ROTZ).
- `TEMP` - Applied temperatures (TEMP, TBOT, TE2, TE3,..., TTOP).
- `PRES` - Applied fluid pressures.
- `V` - Applied flow velocities (VX, VY, VZ).
- `VOLT` - Applied voltages.
- `MAG` - Applied scalar magnetic potentials.
- `A` - Applied vector magnetic potentials.
- `CONC` - Concentration.
- `CHRG` - Applied electric charge.
- `F or FORC` - Applied structural forces (FX, FY, FZ).
- `M or MOME` - Applied structural moments (MX, MY, MZ).
- `HEAT` - Applied heat flows (HEAT, HBOT, HE2, HE3,..., HTOP).
- `FLOW` - Applied fluid flow.
- `AMPS` - Applied current flow.
- `FLUX` - Applied magnetic flux.
- `CSG` - Applied magnetic current segments.
- `RATE` - Diffusion flow rate.
- `MAST` - Master degrees of freedom.
- `CP` - Coupled nodes.
- `CE` - Nodes in constraint equations.
- `NFOR` - POST1 nodal forces.
- `NMOM` - POST1 nodal moments
- `RFOR` - POST1 reaction forces.
- `RMOM` - POST1 reaction moments (MX, MY, MZ).
- `PATH` - Path geometry (undistorted) associated with the [[path|PATH]] command after a [[pdef|PDEF]] or [[pvect|PVECT]] command has been issued.
- `ACEL` - Global acceleration (ACELX, ACELY, ACELZ vector).
- `OMEG` - Global angular velocity (OMEGX, OMEGY, OMEGZ vector) and acceleration (DOMEGX, DOMEGY, DOMEGZ vector).
- `ALL` - Represents all appropriate labels.

**key**

Symbol key:

- `0` - Do not show symbol.
- `1` - Show symbol.
- `2` - Plot value next to symbol.

**min_**: Minimum value in a range of values plotted on screen.

**max_**: Maximum value in a range of values plotted on screen.

**abs_**: Absolute number. If `KEY` = 2 and `ABS` = 0, a number falling between the `MIN` and `MAX` is displayed. If `ABS` is not specified, it defaults to 0. If `KEY` = 2 and `ABS` = 1, an absolute value falling between the `MIN` and `MAX` is displayed. `ABS` = 1 lets you eliminate the display of numbers whose absolute values are less than a desired tolerance. For example, if `ABS` = 1, `MIN` = 10 and `MAX` = 1e8, values such as.83646 and -5.59737 are not displayed.

## Notes

The **/PBC** command adds degree of freedom constraint, force load, and other symbols to displays.

Symbols are applied to the selected nodes only. All arrow and arrowhead symbols are oriented in the nodal coordinate system and lie in two perpendicular planes. Force arrows are scaled proportional to their magnitude. (If `KEY` = 1, use [[vscale|/VSCALE]] to change arrow length.) For scalar quantities, the specific component direction (that is, x, y, or z) of the symbol has no meaning, but the positive or negative sense (for example, positive or negative x) represents a positive or negative scalar value, respectively.

The effects of the **/PBC** command are not cumulative (that is, the command does not modify an existing setting from a previously issued **/PBC** command). If you issue multiple **/PBC** commands during an analysis, only the setting specified by the most recent **/PBC** command applies.

Use [[pstatus|/PSTATUS]] or **/PBC**,STAT to display settings. Use **/PBC**,DEFA to reset all specifications back to default. See the [[psf|/PSF]] and [[pbf|/PBF]] commands for other display symbols.

In a [cyclic symmetry analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/cycsym_example.html), the **/PBC** command is deactivated when [cyclic expansion](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycmodalans.html#eqb90240e8-a774-4a6b-8243-74b9d8bf8886) is active ( [[cycexpand|/CYCEXPAND]],,ON). To view boundary conditions on the [base sector](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycbasesect.html#cycsym_modeling_mistuning), deactivate cyclic expansion ( [[cycexpand|/CYCEXPAND]],,OFF) and issue this command: **/PBC**,ALL,,1

Issuing the command **/PBC**,PATH,,1 displays all defined paths.

The **/PBC** command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PBC.html
