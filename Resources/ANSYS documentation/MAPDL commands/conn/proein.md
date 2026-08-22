---
apdl: "~PROEIN"
method: proein
group: conn
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.conn.Conn.proein
generated: 2026-08-22
tags: [mapdl-command]
---

# ~PROEIN

PyMAPDL: `mapdl.proein(name='', extension='', path='', proecomm='', **kwargs)`

Transfers a Creo Parametric part into the ANSYS program.

## Parameters

**name**: The name of the Creo Parametric part to be imported, which cannot exceed 64 characters in length and must begin with an alphanumeric character. Special characters such as `&` `-` and `*` and spaces are not permitted in the part name.

**extension**: The general Creo Parametric extension format is prt for parts and asm for assemblies.

**path**: Full path name to the directory containing the part. The default is the current working directory.

**proecomm**: The start command for the version of Creo Parametric you are using. proe1 is the default command. Note that the full path name to the Creo Parametric command need not be used here if the path had been included in the PATH variable. The Creo Parametric command name is set by the PROE_START_CMD162 environment variable.

## Notes

More information on importing Creo Parametric parts is available in Creo Parametric (formerly Pro/ENGINEER) in the Connection User's Guide.
