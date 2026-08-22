---
apdl: "~SATIN"
method: satin
group: conn
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.conn.Conn.satin
generated: 2026-08-22
tags: [mapdl-command]
---

# ~SATIN

PyMAPDL: `mapdl.satin(name='', extension='', path='', entity='', fmt='', nocl='', noan='', **kwargs)`

Transfers a .SAT file into the ANSYS program.

## Parameters

**name**: The name of a valid .SAT file, created with a supported version of ACIS. The first character of the file name must be an alphanumeric. Special characters such as `&` `-` and `*` and spaces are not permitted in the part name. See File Names in the Command Reference for more information about ANSYS file naming conventions.

**extension**: The extension for the file. The default extension is .sat.

**path**: The path name of the directory in which the file resides enclosed in single quotes. The default path name is the current working directory.

**entity**

Entity to be imported.

SOLIDS  
Solids only, imported as ANSYS volumes (Not implemented, imports All).

SURFACES  
Surfaces only, imported as ANSYS areas (Not implemented, imports All).

WIREFRAME  
Wireframe only, imported as ANSYS lines (Not implemented, imports All).

ALL  
All entities. Use this option when the file contains different types of entities.

**fmt**

The format in which ANSYS will store the model.

0  
Neutral format (default). Defeaturing after import is restricted.

1  
Solid format; this allows defeaturing after import.

**nocl**

Remove tiny objects.

0  
Remove tiny objects without checking model validity (default).

1  
Do not remove tiny objects.

**noan**

Perform an ACIS analysis of the model.

0  
Analyze the model (default).

1  
Do not analyze the model.

## Notes

More information on importing ACIS parts is available in ACIS in the Connection User's Guide.
