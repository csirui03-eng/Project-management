---
apdl: "SFBEAM"
method: sfbeam
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_surface_loads.FeSurfaceLoads.sfbeam
generated: 2026-08-22
tags: [mapdl-command]
---

# SFBEAM

PyMAPDL: `mapdl.sfbeam(elem='', lkey='', lab='', vali='', valj='', val2i='', val2j='', ioffst='', joffst='', lenrat='', **kwargs)`

Specifies surface loads on beam and pipe elements.

## Parameters

**elem**: Element to which surface load is applied. If ALL, apply load to all selected beam elements ( [[esel|ESEL]] ). If `Elem` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may be substituted in `Elem`.

**lkey**: Load key associated with surface load (defaults to 1). Load keys (1, 2, 3, etc.) are listed under "Surface Loads" in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). For beam and some pipe elements, the load key defines the load orientation.

**lab**: Valid surface load label. Load labels are listed under "Surface Loads" in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). Structural labels: PRES (pressure).

**vali**, **valj**: Surface load values at nodes I and J. If `VALJ` is blank, it defaults to `VALI`. If `VALJ` is zero, a zero is used.

**val2i**, **val2j**: Second surface load values at nodes I and J. Currently not used.

**ioffst**, **joffst**: Offset distance from node I (toward node J) where `VALI` is applied, and offset distance from node J (toward node I) where `VALJ` is applied, respectively.

**lenrat**

Offset distance flag:

- `0` - Offset is in terms of length units (default).
- `1` - Offset is in terms of a length ratio (0.0 to 1.0).

## Notes

Specifies surface loads on the selected beam elements. Distributed loads are applied on a force-per- length basis (that is, the width of the underlying element is not considered). To list and delete surface loads applied with this command, use the [[sfelist|SFELIST]] and [[sfedele|SFEDELE]] commands, respectively.

If no offset values ( `IOFFSET` and `JOFFSET` ) are specified, the load is applied over the full element length. Values may also be input as length fractions, depending on the `LENRAT` setting. For example, assuming a line length of 5.0, an `IOFFST` of 2.0 with `LENRAT` = 0 or an `IOFFST` of 0.4 with `LENRAT` = 1 represent the same point. If `JOFFST` = -1, `VALI` is assumed to be a point load at the location specified via `IOFFST`, and `VALJ` is ignored. ( `IOFFSET` cannot be equal to -1.) The offset values are stepped even if you issue a [[kbc|KBC]],0 command.

Offsets are only available for element types `BEAM188` and `PIPE288` if using the cubic shape function (KEYOPT(3) = 3) for those element types.

To accumulate (add) surface loads applied with this command, use the [[sfcum|SFCUM]],,ADD command. Use the same offset values used on the previous **SFBEAM** command (for a given element face); otherwise, the loads do not accumulate. If no offsets are specified, the command applies the previous offset values.

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFBEAM.html
