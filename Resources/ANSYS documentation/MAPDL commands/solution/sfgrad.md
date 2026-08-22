---
apdl: "SFGRAD"
method: sfgrad
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_surface_loads.FeSurfaceLoads.sfgrad
generated: 2026-08-22
tags: [mapdl-command]
---

# SFGRAD

PyMAPDL: `mapdl.sfgrad(lab='', slkcn='', sldir='', slzer='', slope='', **kwargs)`

Specifies a gradient (slope) for surface loads.

## Parameters

**lab**

Valid surface load label. Load labels are listed under "Surface Loads" in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

(table not available in the PyMAPDL source, see the Ansys help page)

Thermal labels CONV and HFLUX are mutually exclusive.

**slkcn**: Reference number of slope coordinate system (used with `Sldir` and `SLZER` to determine COORD). Defaults to 0 (the global Cartesian coordinate system).

**sldir**

Slope direction in coordinate system `SLKCN` :

- `X` - Slope is along X direction (default). Interpreted as R direction for non-Cartesian coordinate systems.
- `Y` - Slope is along Y direction. Interpreted as θ direction for non-Cartesian coordinate systems.
- `Z` - Slope is along Z direction. Interpreted as Φ direction for spherical or toroidal coordinate systems.

**slzer**: Coordinate location (degrees for angular input) where slope contribution is zero (CVALUE = VALUE). Allows the slope contribution to be shifted along the slope direction. For angular input, `SLZER` should be between ±180° if the singularity ( [[cscir|CSCIR]] ) is at 180° and should be between 0° and 360° if the singularity is at 0°.

**slope**: Slope value (load per unit length or per degree).

## Notes

Specifies a gradient (slope) for surface loads. All surface loads issued with the [[sf|SF]], [[sfe|SFE]], [[sfl|SFL]], or [[sfa|SFA]] commands while this specification is active will have this gradient applied (for complex pressures, only the real component will be affected; for convections, only the bulk temperature will be affected). The load value, CVALUE, calculated at each node is:

CVALUE = VALUE + ( `SLOPE` X (COORD- `SLZER` ))

where VALUE is the load value specified on the subsequent [[sf|SF]], [[sfe|SFE]], [[sfl|SFL]], or [[sfa|SFA]] commands and COORD is the coordinate value (in the `Sldir` direction of coordinate system `SLKCN` ) of the node. Only one **SFGRAD** specification may be active at a time (repeated use of this command replaces the previous specification with the new specification). Issue **SFGRAD** (with blank fields) to remove the specification. Issue **SFGRAD**,STAT to show the current command status. The **SFGRAD** specification (if active) is removed when the [[lsread|LSREAD]] (if any) command is issued.

**SFGRAD** does not work for tabular boundary conditions.

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFGRAD.html
