---
apdl: "VFCO"
method: vfco
group: aux12
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux12.radiosity_solver.RadiositySolver.vfco
generated: 2026-08-22
tags: [mapdl-command]
---

# VFCO

PyMAPDL: `mapdl.vfco(action='', encl='', level='', **kwargs)`

Controls the use and level of view factor condensation for symmetric radiation.

## Parameters

**action**

Action to be performed:

- `DEFINE` - Defines the level of view factor condensation (default).
- `CLEAR` - Resets the level of view factor condensation to 0 for all enclosures. All subsequent arguments are ignored.
- `STATUS` - Outputs the `LEVEL` of view factor condensation for each enclosure in the model.

**encl**: Previously defined enclosure number for the view factor adjustment.

**level**

Key that controls the level of condensation used in calculating the view factor matrix for models with symmetry. Efficiency gains increase with increasing values of `LEVEL`.

- `0` - View factor condensation is turned off (default). The view factor matrix is calculated for all facets, as described in.
- `1` - View factor condensation is turned on. With condensation on, view factors for dependent facets are not calculated, which reduces solution time for models with symmetry. The view factor matrix is calculated only for independent facets as described in. This option achieves better efficiency than `LEVEL` = 0. Element NMISC data is written to the results file for both independent and dependent facets. [[get|*GET]],,RAD,,NETHF, which also uses element fluxes, is based on independent and dependent facets.
- `2` - This option achieves even more efficiency gains than `LEVEL` = 1, but it requires more memory and loses some information. Note that when `LEVEL` = 2 is used, dependent facets are unselected, and no element NMISC data is written to the results file for dependent facets. The same is true for [[get|*GET]],,RAD,,NETHF, which also uses element fluxes and is based on independent facets only.

## Notes

If view factor condensation is turned on ( **VFCO**, `ENCL`,1 or **VFCO**, `ENCL`,2):

- The dependent facets do not participate in the solution, and only the independent view factors are calculated as described in.
- The problem is reduced to solving only for the independent radiosity flux as described in [Radiosity Equations Simplified for Models with Symmetry](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_heat5.html#eqd7803bd4-5251-4d80-bd90-e01d7fdcb8bb)
- The [[vfsm|VFSM]] command operates on the condensed view factor matrix.

**VFCO** must be issued before the view factors are computed by issuing either [[vfopt|VFOPT]],NEW or [[solve|SOLVE]].

**Example Usage** [Example of a 3D Open Enclosure with Symmetry: Radiation Analysis with Condensed View Factor Calculation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/the_example_rad_condensedVF.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VFCO.html
