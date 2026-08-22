---
apdl: "~UGIN"
method: ugin
group: conn
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.conn.Conn.ugin
generated: 2026-08-22
tags: [mapdl-command]
---

# ~UGIN

PyMAPDL: `mapdl.ugin(name='', extension='', path='', entity='', layer='', fmt='', **kwargs)`

Transfers an NX part into the ANSYS program.

## Parameters

**name**: The file name of the NX part to be imported, which cannot exceed 64 characters in length. The path name must begin with an alphanumeric character. Special characters such as &, -, and \* are not permitted in the part name.

**extension**: The NX part file extension. The default is .prt.

**path**: The full path name to the directory containing the part, enclosed in single quotes; for example, '/ug_parts'. The default is the current working directory.

**entity**

Entity to be imported.

0 or Solid  
Solids only, imported as ANSYS volumes (the default).

1 or Surface  
Surfaces only, imported as ANSYS areas.

2 or Wireframe  
Wireframe only, imported as ANSYS lines.

3 or All  
All entities. Use this option when the part contains entities that may not be attached to each other, such as a solid in one location and a surface in another.

**layer**: The number(s) assigned to the layer(s) to be imported. You can import one layer or a range of layers (designated by hyphens). Defaults to 1-256 (all layers).

**fmt**

The format in which ANSYS will store the model.

0  
Neutral format (default). Defeaturing after import is restricted.

1  
Solid format; this allows defeaturing after import.

## Notes

More information on importing NX parts is available in UG/NX in the Connection User's Guide.
