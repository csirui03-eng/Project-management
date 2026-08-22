---
apdl: "CMPLOT"
method: cmplot
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.components.Components.cmplot
generated: 2026-08-22
tags: [mapdl-command]
---

# CMPLOT

PyMAPDL: `mapdl.cmplot(label='', entity='', keyword='', **kwargs)`

Plots the entities contained in a component or assembly.

## Parameters

**label**

Name of the component or assembly to be plotted.

- `(blank)` - All selected components and assemblies are plotted (default). If fewer than 11 components are selected, then all are plotted. If more than 11 components are selected, then only the first 11 are plotted.
- `ALL` - All selected components are plotted. If number of selected components is greater than 11, then the legend showing component names will not be shown.
- `N` - Next set of defined components and assemblies is plotted.
- `P` - Previous set of defined components and assemblies is plotted.
- `Cname` - The specified component or assembly is plotted.
- `SetNo.` - The specified set number is plotted.

**entity**

If `Label` is BLANK or ALL, then the following entity types can be specified:

- `VOLU` - Plot the volume components only.
- `AREA` - Plot the area components only.
- `LINE` - Plot the line components only.
- `KP` - Plot the keypoint components only.
- `ELEM` - Plot the element components only.
- `NODE` - Plot the node components only.

**keyword**: For `Keyword` = ALL, plot the specified component name in the `Label` field in the context of all entities of the same type. Not valid if `Label` field is BLANK or ALL.

## Notes

Components are plotted with their native entities. For assemblies, all native entities for the underlying component types are plotted simultaneously. Although more components can be plotted, the legend displays only 11 at a time. When more than eleven are plotted, the legend is not displayed.

Possible usage:

- **CMPLOT**, `CNAME` - Plots the specified component (if selected).
- **CMPLOT**, `CNAME`, ALL - Plot component in the context of all other selected entity components of the same type as the component.
- **CMPLOT** - Plot the first eleven selected components.
- **CMPLOT**,ALL - Plot all selected components.
- **CMPLOT**,N or **CMPLOT**,P - Plot next or previous set of eleven components.
- **CMPLOT**,ALL, `Entity` - Plot all selected components of type specified in `Entity`.
- **CMPLOT**, `Entity` - Plot components of type specified in `Entity`, from the first eleven components.
- **CMPLOT**,N, `Entity` - Plot components of type specified in `Entity`, if any, from the next set of eleven components (substitute P for N to plot from previous set).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMPLOT.html
