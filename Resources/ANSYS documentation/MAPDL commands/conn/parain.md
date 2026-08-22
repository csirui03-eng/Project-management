---
apdl: "~PARAIN"
method: parain
group: conn
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.conn.Conn.parain
generated: 2026-08-22
tags: [mapdl-command]
---

# ~PARAIN

PyMAPDL: `mapdl.parain(name='', extension='', path='', entity='', fmt='', scale='', **kwargs)`

Transfers a Parasolid file into the ANSYS program.

## Parameters

**name**: The name of a valid Parasolid file. The first character of the file name must be an alphanumeric.

**extension**: The extension for the file. The default extension is .x_t on a PC or .xmt_txt on a Linux system. Parasolid files are compatible across systems, and do not need to be renamed to be used on another platform.

**path**: The path name of the directory in which the file resides, enclosed in single quotes. The default path name is the current working directory.

**entity**

Entity to be imported:

SOLIDS  
Solids only, imported as ANSYS volumes (default)

SURFACES  
Surfaces only, imported as ANSYS areas.

WIREFRAME  
Wireframe only, imported as ANSYS lines.

ALL  
All entities. Use this option when the file contains more than one type of entity.

**fmt**

Sets the format in which ANSYS will store the model

0  
Neutral format (default). Defeaturing after import is restricted. Use this option if you need to scale a model to a specific unit of measure (other than meters).

1  
Solid format; this allows defeaturing after import.

**scale**

Allows scaling for the model

0  
Do not rescale the model; retain the default Parasolid setting of meters (default).

1  
Scale the model if warranted by the model size.

## Notes

More information on importing Parasolid parts is available in Parasolid in the Connection User's Guide.
