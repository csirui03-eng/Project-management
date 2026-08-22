---
apdl: "SFFUN"
method: sffun
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_surface_loads.FeSurfaceLoads.sffun
generated: 2026-08-22
tags: [mapdl-command]
---

# SFFUN

PyMAPDL: `mapdl.sffun(lab='', par='', par2='', **kwargs)`

Specifies a varying surface load.

## Parameters

**lab**

Valid surface load label. Load labels are listed under "Surface Loads" in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). Issue **SFFUN**,STATUS to list current command settings.

(table not available in the PyMAPDL source, see the Ansys help page)

Thermal labels CONV and HFLUX are mutually exclusive.

**par**: Parameter containing list of surface load values. If `Lab` = CONV, values are typically the film coefficients and `Par2` values (below) are typically the bulk temperatures.

**par2**: Parameter containing list of second surface load values (if any). If `Lab` = CONV, the `Par2` values are typically the bulk temperatures. `Par2` is not used for other surface load labels.

## Notes

Specifies a surface load "function" to be used when the [[sf|SF]] or [[sfe|SFE]] command is issued. The function is supplied through an array parameter vector which contains nodal surface load values. Node numbers are implied from the sequential location in the array parameter. For example, a value in location 11 applies to node 11. The element faces are determined from the implied list of nodes when the [[sf|SF]] or [[sfe|SFE]] command is issued. Zero values should be supplied for nodes that have no load. A tapered load value may be applied over the element face. These loads are in addition to any loads that are also specified with the [[sf|SF]] or [[sfe|SFE]] commands. Issue **SFFUN** (with blank remaining fields) to remove this specification. Issue **SFFUN**,STATUS to list current settings.

Starting array element numbers must be defined for each array parameter vector. For example, **SFFUN**,CONV,A(1,1),A(1,2) reads the first and second columns of array A (starting with the first array element of each column) and associates the values with the nodes. Operations continue on successive column array elements until the end of the column. Another example to show the order of the commands:

``` apdl
*dim,nodepres,array,2
nodepres(1)=11,12
/prep7
et,1,42
n,1
n,2,1
n,3,1,1
n,4,,1
e,1,2,3,4
sfe,1,1,pres,1,3
sfelist ! expected answer: 3 at both nodes 1 and 2
sfedel,all,pres,all
sffun,pres, nodepres(1)
sfe,1,1,pres,1,5
sfelist ! expected answer: 5+11=16 at node 1, 5+12=17 at node 2
fini
```

**SFFUN** does not work for tabular boundary conditions.

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFFUN.html
