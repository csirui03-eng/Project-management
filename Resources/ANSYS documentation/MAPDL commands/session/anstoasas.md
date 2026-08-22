---
apdl: "ANSTOASAS"
method: anstoasas
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.files.Files.anstoasas
generated: 2026-08-22
tags: [mapdl-command]
---

# ANSTOASAS

PyMAPDL: `mapdl.anstoasas(fname='', key='', **kwargs)`

Creates an ASAS input file from the current Mechanical APDL model.

## Parameters

**fname**: ASAS file name. Defaults to `Jobname`.

**key**

Key indicating type of file to produce:

- `0` - ASAS file for use by Ansys Aqwa (no loads written). Creates the file `Fname`.asas.
- `1` - ASAS file (all data written, including loads). Creates the file `Fname`.asas.
- `2` - ASAS(NL) file. Creates the file `Fname`.asnl.

## Notes

This command creates an input file for the Ansys Asas Finite Element Analysis System from the model and loads currently in the database, based on the currently selected set of elements. Most common structural element types are written, as well as sections (or real constants), materials, boundary conditions and loads, and solution and load step options.

**Data Written**

The following data is written:

- Solution control options
- Nodes
- Elements
- Material data
- Geometry data
- Section data
- Mechanical APDL element components (ASAS sets)
- Boundary conditions
- Loads
- Added mass (via `MASS21` element)

Details are provided in the following sections.

Not all data is written. You must verify the completeness and accuracy of the data. Only loading at the current step is transferred; hence, no load step history is captured.

****Solution Control Options****

The ASAS project name is defined as "Ansys".

The solution control options are converted as follows:

(table not available in the PyMAPDL source, see the Ansys help page)

For conversion to ASAS(NL), the large displacement option is set based on [[nlgeom|NLGEOM]], final load solution time is set based on [[time|TIME]], and sub-step times are set based on [[deltim|DELTIM]] or [[nsubst|NSUBST]] (assuming constant step size).

****Element Data****

If you intend to use the data only with AQWA-WAVE, only the elements that form the wetted surface are required. Selecting these elements before invoking the **ANSTOASAS** command will improve performance. In order for AQWA-WAVE to identify the direction of the wave loading, all elements must be defined by nodes in a clockwise direction. For further information, refer to the AQWA-WAVE manual.

The element types are converted as follows:

(table not available in the PyMAPDL source, see the Ansys help page)

Documentation for this archived element type appears in the [Feature Archive](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/archlegacytheory.html).

****Material Data****

Linear isotropic material conversion is supported for ASAS and ASAS(NL).

****Geometry Data****

The following ASAS element geometry data is supported:

(table not available in the PyMAPDL source, see the Ansys help page)

For all beam elements, the third node position must be explicitly defined. If the position is not defined, the program generates an error code (-1) in the output file.

****Section Data****

No user sections are generated if AQWA-WAVE data is selected.

The following sections are converted for ASAS and ASAS(NL):

(table not available in the PyMAPDL source, see the Ansys help page)

****Boundary Conditions****

The following boundary conditions are converted for ASAS and ASAS(NL):

(table not available in the PyMAPDL source, see the Ansys help page)

****Loads****

No user loading is generated if AQWA-WAVE data is selected. However, a load case (number 1000) is automatically defined to identify the wetted surface of the elements for use by AQWA-WAVE based on the normal surface loads applied to the solid or shell elements.

Pressure loads from `SURF154` elements are converted to equivalent nodal loads for ASAS. For AQWA- WAVE, the `SURF154` pressures are used to identify the wetted surface of the underlying elements. The following loads are converted for ASAS:

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANSTOASAS.html
