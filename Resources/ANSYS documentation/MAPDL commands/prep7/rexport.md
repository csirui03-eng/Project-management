---
apdl: "REXPORT"
method: rexport
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.rexport
generated: 2026-08-22
tags: [mapdl-command]
---

# REXPORT

PyMAPDL: `mapdl.rexport(target='', lstep='', sbstep='', fname='', ext='', **kwargs)`

Exports displacements from an implicit run to ANSYS LS-DYNA.

## Parameters

**target**

The type of analysis run to which displacements are exported.

OFF - Ignore initial displacements.

DYNA - Get initial displacements from an earlier implicit  
(ANSYS) run and export to an explicit ANSYS LS-DYNA run (Default).

**lstep**: Load step number of data to be exported. Defaults to the last load step.

**sbstep**: Substep number of data to be exported. Defaults to the last substep.

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name.

**ext**: Filename extension (eight-character maximum).

## Notes

This command exports the displacements, rotations, and temperatures calculated in an ANSYS implicit analysis into the drelax' file, which is subsequently read in by ANSYS LS-DYNA when a dynamic relaxation or stress initialization is conducted EDDRELAX\`.

This command is not written to the Jobname.CDB file when the CDWRITE command is issued.
