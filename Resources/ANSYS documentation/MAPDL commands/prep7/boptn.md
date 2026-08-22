---
apdl: "BOPTN"
method: boptn
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.boptn
generated: 2026-08-22
tags: [mapdl-command]
---

# BOPTN

PyMAPDL: `mapdl.boptn(lab='', value='', **kwargs)`

Specifies Boolean operation options.

**Command default:**

Input entities will be deleted, and operations with no effect (that is, operations which are valid but which do not cause a change in the input entities, such as adding two non-touching areas) will produce a warning message. The Revision 5.2 Boolean compatibility option will be used.

## Parameters

**lab**

Default/status key:

- `DEFA` - Resets settings to default values.
- `STAT` - Lists status of present settings.

Option to be controlled:

- `KEEP` - Delete or keep input entity option.
- `NUMB` - Output numbering warning message option.
- `NWARN` - No effect warning message option.
- `VERSION` - Boolean compatibility option.

**value**

Option settings if `Lab` = KEEP:

- `NO` - Delete entities used as input with a Boolean operation (default). Entities will not be deleted if meshed or if attached to a higher entity.
- `YES` - Keep input solid modeling entities.

Option settings if `Lab` = NUMB:

- `0` - No warning message will be produced if the output entities of a Boolean operation are numbered based on geometry (default).
- `1` - A warning message will be produced if the output entities of a Boolean operation are numbered based on geometry. (With geometric numbering, re-use of the input with altered dimensions may not produce the same numbering, and later operations in the input may fail or produce unexpected results.)

Option settings if `Lab` = NWARN:

- `0` - A warning message will be produced if a Boolean operation has no effect (default).
- `1` - No warning or error messages will be generated if a Boolean operation has no effect.
- `-1` - An error message will be produced if a Boolean operation has no effect.

Option settings if `Lab` = VERSION:

- `RV52` - Activate the Revision 5.2 compatibility option (default). The 5.2 option can produce different numbering of the entities produced by Boolean operations than the 5.1 option. See Notes below.
- `RV51` - Activate the Revision 5.1 compatibility option. The 5.1 option can produce different numbering of the entities produced by Boolean operations than the 5.2 option. See [[boptn#Notes|BOPTN]] below.

## Notes

Boolean operations at Revision 5.2 may produce a different number of entities than previous revisions of Mechanical APDL. When running input files created in earlier versions of Mechanical APDL, match the Boolean compatibility option (VERSION) to the revision originally used. For instance, if you are running Revision 5.2 and are reading an input file ( [[input|/INPUT]] ) created at Revision 5.1, it is recommended that you set VERSION to RV51 before reading the input.

See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for further details on the functions of the RV51 and RV52 labels.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BOPTN.html
