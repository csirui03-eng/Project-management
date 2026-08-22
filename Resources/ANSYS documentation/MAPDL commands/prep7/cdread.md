---
apdl: "CDREAD"
method: cdread
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.database.Database.cdread
generated: 2026-08-22
tags: [mapdl-command]
---

# CDREAD

PyMAPDL: `mapdl.cdread(option='', fname='', ext='', fnamei='', exti='', **kwargs)`

Reads a file of solid model and database information into the database.

## Parameters

**option**

Selects which data to read:

- `ALL` - Read all geometry, material property, load, and component data (default). Solid model geometry and loads will be read from the file `fnamei.exti`. All other data will be read from the file `fname.ext.` None
- `DB` - Read all database information contained in file `Fname.Ext`. This file should contain all information mentioned above except the solid model loads. If reading a `.CDB` file written with the GEOM option of the [[cdwrite|CDWRITE]] command, element types ( [[et|ET]] ) compatible with the connectivity of the elements on the file must be defined prior to reading.
- `SOLID` - Read the solid model geometry and solid model loads from the file `Fnamei.Exti`. This file could have been written by the [[cdwrite|CDWRITE]] or [[igesout|IGESOUT]] command.
- `COMB` - Read the combined solid model and database information from the file `Fname.Ext.` None

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to `.cdb` if `Fname` is blank.

**fnamei**

Name of the IGES file and its directory path (248 characters maximum, including directory). If you do not specify a directory path, it will default to your working directory and you can use all 248 characters for the file name.

The file name defaults to `Fname`. Used only if `Option` = ALL or SOLID.

**exti**: Filename extension (eight-character maximum). Defaults to IGES if `Fnamei` is blank.

## Notes

This command causes coded files of solid model (in IGES format) and database (in command format) information to be read. These files are normally written by the [[cdwrite|CDWRITE]] or [[igesout|IGESOUT]] command. Note that the active coordinate system in these files has been reset to Cartesian ( [[csys|CSYS]],0).

If a set of data exists prior to the **CDREAD** operation, that data set is offset upward to allow the new data to fit without overlap. The [[nooffset|NOOFFSET]] command allows this offset to be ignored on a set-by-set basis, causing the existing data set to be overwritten with the new data set.

When you write the geometry data using the [[cdwrite|CDWRITE]],GEOM option, you use the **CDREAD**,DB option to read the geometry information.

Using the **CDREAD**,COMB option will not write [[numoff|NUMOFF]] commands to offset entity ID numbers if there is no solid model in the database.

Multiple `.cdb` file imports cannot have elements with real constants in one file and section definitions in another. The section attributes will override the real constant attributes. If you use **CDREAD** to import multiple CDB files, define all of the elements using only real constants, or using only section definitions. Combining real constants and section definitions is not recommended.

If a radiosity mapping data file ( `.rsm` file) was saved by the previous [[cdwrite|CDWRITE]] command, that mapping file must be present in the directory along with the coded geometry file in order for radiosity surface elements ( `SURF251`, `SURF252` ) to be correctly mapped onto the model when **CDREAD** is issued.

If you issue [[cdwrite|CDWRITE]] to import a `.cdb` file containing a [user-defined element](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_USER300.html#user300prodrest), manually insert [[usrelem|USRELEM]] and [[usrdof|USRDOF]] commands in the `.cdb` file to provide the user-defined element characteristics. Insert the two commands after the [[et|ET]] command (defining the user-defined element) and before the `EBLOCK` command. (If multiple element types are defined in the `.cdb` file, insert the [[type|TYPE]] command to select the user-defined element. Place it before [[usrelem|USRELEM]] and [[usrdof|USRDOF]].)

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CDREAD.html
