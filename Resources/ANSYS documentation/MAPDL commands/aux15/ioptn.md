---
apdl: "IOPTN"
method: ioptn
group: aux15
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux15.iges.Iges.ioptn
generated: 2026-08-22
tags: [mapdl-command]
---

# IOPTN

PyMAPDL: `mapdl.ioptn(lab='', val1='', **kwargs)`

Controls options relating to importing a model.

## Parameters

**lab**

Label identifying the import option. The meaning of `VAL1` varies depending on `Lab`.

- `STAT` - List overall status of import facilities, including current option values. `VAL1` is ignored.
- `DEFA` - Set default values for all import options. `VAL1` is ignored.
- `MERG` - Entity merge option. `VAL1` can be:
  - `YES` - Automatic merging is performed (default).
  - `NO` - No merging of entities.
- `SOLID` - Solid option. `VAL1` can be:
  - `YES` - Solid is created automatically (default).
  - `NO` - No solid created.
- `GTOLER` - Entity merging tolerance. If IGES = SMOOTH, the GTOLER, `VAL1` can be:
  - `DEFA` - Use system defaults (default).
  - `FILE` - Use tolerance from the imported file.
  - `n` - A user-specified tolerance value.
- `IGES` - IGES import option. `VAL1` can be:
  - `STAT` - List status of IGES related options in the output window.
  - `SMOOTH (or RV52)` - Use more robust IGES revision 5.2 import function (default).
- `SMALL` - Small areas option. `VAL1` can be:
  - `YES` - Small areas are deleted (default).
  - `NO` - Small areas are retained.

**val1**: Additional input value as described under each `Lab` option.

## Notes

Controls various options during a model file transfer. A global solid model tolerance (GTOLER) can be specified.

The SMALL,YES option (default) delete small areas and can cause geometrical inconsistencies that could cause the import process to abort. Retaining the small areas increases processor time and memory usage.

The data is stored in the standard Mechanical APDL graphics database.

The IGES,SMOOTH (default) option is capable of reading in any rational B-spline curve entity (type 126), or rational B-spline surface entity (type 128) with a degree less than or equal to 20. Attempts to read in B-spline curve or surface entities of degree higher than 20 may result in error messages.

If you issue the [[clear|/CLEAR]] command, the **IOPTN** settings return to their defaults.

For MERG,YES, merging of coincident geometry items is performed automatically when the [[igesin|IGESIN]] command is issued (that is, an internal [[nummrg|NUMMRG]],KP command is issued). The model is merged with the consideration tolerance ( `TOLER` on [[nummrg|NUMMRG]] ) set equal to 0.75 \* the shortest distance between the endpoints of any active line. See the [[nummrg|NUMMRG]] command for more information about the tolerances. In most cases, the default merging is appropriate. Use the **IOPTN** command when you want to:

- Disable merging operations.
- Override the default merging and specify a global solid model tolerance value (GTOLER).
- Disable the automatic creation of solids (SOLID).

The **IOPTN** command should be issued before the [[igesin|IGESIN]] command. You cannot change these options after your model has been imported or created. If you must change the options: Clear the database ( [[clear|/CLEAR]] ) or exit and restart the program.

Set the correct options.

Reimport or recreate the model.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_IOPTN.html
