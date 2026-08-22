---
apdl: "~CATIAIN"
method: catiain
group: conn
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.conn.Conn.catiain
generated: 2026-08-22
tags: [mapdl-command]
---

# ~CATIAIN

PyMAPDL: `mapdl.catiain(name='', extension='', path='', blank='', **kwargs)`

Transfers a CATIA model into the ANSYS program.

## Parameters

**name**: The name of a valid CATIA model, created with CATIA 4.x or lower. The first character of the file name must be an alphanumeric. Special characters such as `&` `-` and `*` and spaces are not permitted in the part name.

**extension**: The extension for the file. The default extension is .model.

**path**: The path name of the directory in which the file resides, enclosed in single quotes. The default path name is the current working directory.

**blank**

Sets whether to import "blanked" entities.

0  
Does not import "blanked" (suppressed) CATIA entities (default).

1  
Imports "blanked" entities. The portions of CATIA data that were suppressed will be included in the import.

## Notes

More information on importing CATIA parts is available in CATIA V4 in the Connection User's Guide.
