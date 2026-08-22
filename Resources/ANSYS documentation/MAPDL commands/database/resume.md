---
apdl: "RESUME"
method: resume
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.set_up.SetUp.resume
generated: 2026-08-22
tags: [mapdl-command]
---

# RESUME

PyMAPDL: `mapdl.resume(fname='', ext='', nopar='', knoplot='', **kwargs)`

Resumes the database from the database file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to DB if `Fname` is blank.

**nopar**

Parameter resume key:

- `0` - All data in the database, including the scalar parameters, are replaced with the data saved on `Jobname.db` (default).
- `1` - All data in the database, except the scalar parameters, are replaced with the data saved on `Jobnamedb`.

**knoplot**: If equal to 1, will suppress automatic plot. Otherwise, if the GUI is on and this **RESUME** command was not read from a file, the selected elements from `Fname` are plotted. (If there are no selected elements, selected nodes are plotted. If no nodes, volumes; if no volumes, areas; if no areas, lines; if no lines, keypoints. If there are no selected keypoints, the screen is erased.)

## Notes

The **RESUME** command resumes a database file into Mechanical APDL. The command causes the database file ( `Jobname.db` ) to be read, thereby resetting the database (including any geometry settings) either a) as it was at the last [[save|SAVE]] command, or b) as it was saved with the last `/EXIT` command, whichever was last.

For multiple load step analyses (because only the data for one load step at a time may reside in the database), the load step data restored to the database will correspond to the load step data written when the save occurred.

If the database file was saved in another Ansys, Inc. product, it may contain element type and [[keyopt|KEYOPT]] specifications which are invalid in the resuming product. Immediately after the database resume is completed, you should redefine these invalid element types and [[keyopt|KEYOPT]] settings to valid ones ( [[et|ET]], [[keyopt|KEYOPT]] ).

The `NOPAR` = 1 option should not be used if array parameters are defined, as existing array parameters might be redefined with arbitrary values. For a more general method of preventing the replacement of both scalar and array parameters, see [[parsav|PARSAV]] and [[parres|PARRES]].)

If a radiosity mapping data file ( `.rsm` file) was saved by the previous [[save|SAVE]] command, that mapping file must be present in the directory along with the database file in order for radiosity surface elements ( `SURF251`, `SURF252` ) to be correctly mapped onto the model when **RESUME** is issued.

This command is valid in any processor. If used in the solution processor, this command is valid only within the first load step.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RESUME.html
