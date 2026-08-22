---
apdl: "OUTGEOM"
method: outgeom
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.outgeom
generated: 2026-08-22
tags: [mapdl-command]
---

# OUTGEOM

PyMAPDL: `mapdl.outgeom(item='', freq='', **kwargs)`

Controls geometry-related data written to the results file.

## Parameters

**item**

Geometry data item for file write control:

- `MAT` - Material Properties.
- `ERASE` - Reset **OUTGEOM** specifications to their default values.
- `STAT` - List the current **OUTGEOM** specifications.

**freq**

Specifies how often to write the specified geometry data:

- `NONE` - Suppress writing of the specified item for all substeps.
- `ALL` - Write the data of the specified item for every substep.

## Notes

The **OUTGEOM** command controls writing of the specified geometry `Item` to the results file. The geometry items correspond to the geometry records that are included in the results file (see the GEO records of the results file as described in ).

The command generates a specification for controlling data storage by either activating storage of the specified geometry item ( `Freq` = ALL) or by suppressing storage of that item ( `Freq` = NONE).

You can issue multiple **OUTGEOM** commands in an analysis. After the initial command creates the storage specification, subsequent **OUTGEOM** commands modify the specification set. The command processes your specifications in the order in which you input them. If you specify a given `Item` twice, output is based upon the last specification.

In addition to **OUTGEOM**, [[outpr|OUTPR]] and [[outres|OUTRES]] also control solution output. You can issue up to 50 of these output-control commands (any combination of the three) in an analysis.

**OUTGEOM**,ERASE erases the existing output specifications and resets the counted number of **OUTGEOM** commands to zero.

When material property information is not written to the results file ( **OUTGEOM**,MAT,NONE), clearing the database via [[clear|/CLEAR]] and reading in a set of data in the general postprocessor ( [[post1|/POST1]] ) via the [[set|SET]] command results in no material property data being stored in the database. In this case, the lack of material data prevents a successful solve from occurring with the modified database, and the results file is only applicable for carrying out post-processing.

The **OUTGEOM** command is also valid in [[prep7|/PREP7]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_OUTGEOM.html
