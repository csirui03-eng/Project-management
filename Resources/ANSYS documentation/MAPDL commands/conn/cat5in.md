---
apdl: "~CAT5IN"
method: cat5in
group: conn
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.conn.Conn.cat5in
generated: 2026-08-22
tags: [mapdl-command]
---

# ~CAT5IN

PyMAPDL: `mapdl.cat5in(name='', extension='', path='', entity='', fmt='', nocl='', noan='', **kwargs)`

Transfers a .CATPart file into the ANSYS program.

## Parameters

**name**: The name of a valid .CATPart file, created with CATIA Version 5.0. The first character of the file name must be an alphanumeric.

**extension**: The extension for the file. The default extension is .CATPart.

**path**: The path name of the directory in which the file resides enclosed in single quotes. The default path name is the current working directory.

**entity**

Entity to be imported.

SOLIDS  
Solids only, imported as ANSYS volumes (default).

SURFACES  
Surfaces only, imported as ANSYS areas.

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

Perform an analysis of the model.

0  
Analyze the model (default).

1  
Do not analyze the model.

## Notes

If defeaturing is specified (FMT = 1), this command must be the last line of any file, script, or other interactive input.

More information on importing CATIA Version 5 parts is available in CATIA V5 in the Connection User's Guide.
