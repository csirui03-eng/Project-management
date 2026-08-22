---
apdl: "BFE"
method: bfe
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_body_loads.FeBodyLoads.bfe
generated: 2026-08-22
tags: [mapdl-command]
---

# BFE

PyMAPDL: `mapdl.bfe(elem='', lab='', stloc='', val1='', val2='', val3='', val4='', **kwargs)`

Defines an element body-force load.

## Parameters

**elem**: The element to which body load applies. If ALL, apply to all selected elements ( [[esel|ESEL]] ). A component name may also be substituted for `Elem`.

**lab**

Valid body load label. Valid labels are also listed for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html) under "Body Loads" in the input table.

(table not available in the PyMAPDL source, see the Ansys help page)

**stloc**: Starting location for entering `VAL` data, below. For example, if `STLOC` = 1, data input in the `VAL1` field applies to the first element body load item available for the element type, `VAL2` applies to the second element item, etc. If `STLOC` = 5, data input in the `VAL1` field applies to the fifth element item, etc. Defaults to 1.

**val1**, **val2**, **val3**, **val4**

For `Lab` = TEMP, FLUE, DGEN, HGEN, and CHRGD, `VAL1` - `VAL4` represent body load values at the starting location and subsequent locations (usually nodes) in the element. `VAL1` can also represent a table name for use with tabular boundary conditions. Enter only `VAL1` for a uniform body load across the element. For nonuniform loads, the values must be input in the same order as shown in the input table for the element type. Values initially default to the [[bfunif|BFUNIF]] value (except for CHRGD which defaults to zero). For subsequent specifications, a blank leaves a previously specified value unchanged; if the value was not previously specified, the default value as described in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html) is used.

For `Lab` = JS and `STLOC` = 1, `VAL1`, `VAL2` and `VAL3` are the X, Y, and Z components of current density (in the element coordinate system), and `VAL4` is the phase angle.

For `Lab` = EF and `STLOC` = 1, `VAL1`, `VAL2`, and `VAL3` are the X, Y, and Z components of electric field (in the global Cartesian coordinate system).

If `Lab` = FVIN in a unidirectional Mechanical APDL to Ansys CFX analysis, `VAL2` is the volume interface number (not available from within the GUI), and `VAL1`, `VAL3`, and `VAL4` are not used.

For `Lab` = FORC and `STLOC` = 1, `VAL1`, `VAL2`, and `VAL3` are the real X, Y, and Z components of force density (in the global Cartesian coordinate system).

For analyses that allow complex input, if `Lab` = FORC and `STLOC` = 4, `VAL1`, `VAL2`, and `VAL3` are the imaginary X, Y, and Z components of force density (in the global Cartesian coordinate system).

## Notes

Defines an element body-force load (such as the temperature in a structural analysis or the heat- generation rate in a thermal analysis). Body loads and element specific defaults are described for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). If both the [[bf|BF]] and **BFE** commands are used to apply a body-force load to an element, the **BFE** command takes precedence.

Imaginary values for FORC loading via **BFE** is supported by current-technology solid elements ( `PLANE182`, `PLANE183`, `SOLID185`, `SOLID186`, `SOLID187`, and `SOLID285` ) and reinforcing elements ( `REINF263`, `REINF264`, and `REINF265` ). Use only for modal or harmonic analyses. Large-deflection effects must be disabled ( [[nlgeom|NLGEOM]],OFF).

The following topics for applying HGEN loading via the **BFE** command are available:

For HGEN loading on layered thermal solid elements `SOLID278` / `SOLID279` (KEYOPT(3) = 1 or 2), or layered thermal shell elements `SHELL131` / `SHELL132` (KEYOPT(3) = 1), `STLOC` refers to the layer number (not the node). In such cases, specify `VAL1` through `VAL4` to specify the heat-generation values for the appropriate layers. Heat generation is constant over the layer.

For HGEN loading on [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) elements `REINF263`, `REINF264`, and `REINF265`, `STLOC` refers to the corner locations of the reinforcing members (individual reinforcings):

- `REINF263` and `REINF264` : Specify `VAL1` and `VAL2` for each member. For tables, specify `VAL1` only.
- `REINF265` : Specify `VAL1`, `VAL2`, `VAL3`, and `VAL4` for each member. For tables, specify `VAL1` only.

For FORC loading on reinforcing elements, `STLOC` refers to real ( `STLOC` = 1) or imaginary ( `STLOC` = 4) components.

When using the [standard method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strreinfworkflow.html#) for defining reinforcing, this is the only way to apply a body load (HGEN or FORC) on the reinforcing members created after generating the REINF `nnn` reinforcing elements ( [[ereinf|EREINF]] ). If applying FORC loading, Mechanical APDL applies a uniform load to all reinforcing members if there are multiple members in selected elements.

When using the [mesh-independent method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strreinfworkflow.html#) for defining reinforcing, you can apply a body load on the reinforcing members in the same way. The preferred method, however, is to apply loads on the `MESH200` elements (via **BFE** or [[bf|BF]] for HGEN, BFE for FORC) before generating the REINF `nnn` reinforcing elements ( [[ereinf|EREINF]] ). Mechanical APDL maps the loads from the `MESH200` elements to the newly generated REINF `nnn` reinforcing elements automatically. If you need to apply the loads after generating the reinforcing elements, apply them to `MESH200` elements and issue [[bfport|BFPORT]] to transfer the loads to the reinforcing members.

You can specify a table name ( `VAL1` ) when using temperature (TEMP), diffusing substance generation rate (DGEN), heat generation rate (HGEN), and current density (JS) body load labels.

For the body-force-density label (FORC), you can specify a table for any of the `VAL1` through `VAL3` arguments. Both 1D and 2D tables are valid; however, only 1D tables are valid in mode- superposition harmonic and mode-superposition transient analyses.

Enclose the table name ( `tabname` ) in percent signs (%), for example :

**BFE**, `Elem`, `Lab`, `STLOC`,`tabname`

Use the [[dim|*DIM]] command to define a table. For information on primary variables for each load type, see [Applying Loads Using Tabular Input](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS2_6.html#gbas5dexample)

For `Lab` = TEMP, each table defines `NTEMP` temperatures, as follows:

- For layered elements, `NTEMP` is the number of layer interface corners that allow temperature input.
- For non-layered elements, `NTEMP` is the number of corner nodes.

The temperatures apply to element items with a starting location of `STLOC` + `n`, where n is the value field location ( `VALn` ) of the table name input.

For layered elements, a single **BFE** command returns temperatures for one layer interface. Multiple **BFE** commands are necessary for defining all layered temperatures.

For beam, pipe and elbow elements that allow multiple temperature inputs per node, define the tabular load for the first node only (Node I), as loads on the remaining nodes are applied automatically. For example, to specify a tabular temperature load on a `PIPE288` element with the through-wall-gradient option (KEYOPT(1) = 0), the **BFE** command looks like this:

**BFE**, `Elem`,TEMP,1,`tabOut`, `tabIn%`

where %

> `tabOut` and `tabIn` and are the tables applied to the outer and inner surfaces of the pipe

wall, respectively.

When a tabular function load is applied to an element, the load does not vary according to the positioning of the element in space.

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFE.html
