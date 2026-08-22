---
apdl: "WPSTYL"
method: wpstyl
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.working_plane.WorkingPlane.wpstyl
generated: 2026-08-22
tags: [mapdl-command]
---

# WPSTYL

PyMAPDL: `mapdl.wpstyl(snap='', grspac='', grmin='', grmax='', wptol='', wpctyp='', grtype='', wpvis='', snapang='', **kwargs)`

Controls the display and style of the working plane.

## Parameters

**snap**: Snap increment for a locational pick (1E-6 minimum). If -1, turn off snap capability. For example, a picked location of 1.2456 with a snap of 0.1 gives 1.2, with 0.01 gives 1.25, with 0.001 gives 1.246, and with 0.025 gives 1.250 (defaults to 0.05).

**grspac**: Graphical spacing between grid points. For graphical representation only and not related to snap points (defaults to 0.1).

**grmin**, **grmax**: Defines the size of a square grid (if `WPCTYP` = 0) to be displayed over a portion of the working plane. The opposite corners of the grid will be located at grid points nearest the working plane coordinates of ( `GRMIN`, `GRMIN` ) and ( `GRMAX`, `GRMAX` ). If a polar system ( `WPCTYP` = 1), `GRMAX` is the outside radius of grid and `GRMIN` is ignored. If `GRMIN` = `GRMAX`, no grid will be displayed (defaults to -1.0 and 1.0 for `GRMIN` and `GRMAX` respectively).

**wptol**: The tolerance that an entity's location can deviate from the specified working plane, while still being considered on the plane. Used only for locational picking of vertices for polygons and prisms (defaults to 0.003).

**wpctyp**

Working plane coordinate system type:

- `0` - Cartesian (default). If working plane tracking is on ( [[csys|CSYS]],4), the updated active coordinate system will also be Cartesian.
- `1` - Polar. If working plane tracking is on, the updated active coordinate system will be cylindrical.
- `2` - Polar. If working plane tracking is on, the updated active coordinate system will be spherical.

**grtype**

Grid type:

- `0` - Grid and WP triad.
- `1` - Grid only.
- `2` - WP triad only (default).

**wpvis**

Grid visibility:

- `0` - Do not show `GRTYPE` entities (grid and/or triad) (default).
- `1` - Show `GRTYPE` entities. Cartesian working planes will be displayed with a Cartesian grid, polar with a polar grid.

**snapang**: Snap angle (0-180) in degrees. Used only if `WPCTYP` = 1 or 2. Defaults to 5 degrees.

## Notes

Use **WPSTYL**,DEFA to reset the working plane to its default location and style. Use **WPSTYL**,STAT to list the status of the working plane. Blank fields will keep present settings.

It is possible to specify `SNAP` and `WPTOL` values that will cause conflicts during picking operations. Check your values carefully, and if problems are noted, revert to the default values.

**WPSTYL** with no arguments will toggle the grid on and off. The working plane can be displayed in the non-GUI interactive mode only after issuing a [[plopts|/PLOPTS]],WP,1 command. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for more information on working plane tracking. See [[plopts|/PLOPTS]] command for control of hidden line working plane.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_WPSTYL.html
