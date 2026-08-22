---
apdl: "RESWRITE"
method: reswrite
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.reswrite
generated: 2026-08-22
tags: [mapdl-command]
---

# RESWRITE

PyMAPDL: `mapdl.reswrite(fname='', cflag='', **kwargs)`

Appends results data from the database to a results file.

## Parameters

**fname**

File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name.

The file name extension varies as follows:

- `.rst` for structural, fluid, or coupled-field analyses
- `.rth` for thermal or electrical analyses
- `.rmg` for magnetic analyses

**cflag**

- `0` - The complex results flag is set to 0 in the results file header. This is the default option.
- `1` - The complex results flag is set to 1 in the results file header.

## Notes

The **RESWRITE** command appends a data set to the specified file by writing the results data currently in the database. If the intended results file does not exist, it will be created and will include the geometry records. The current load step, substep, and time (or frequency) value are maintained. All data (summable and nonsummable) are written.

When complex results are appended, `cFlag` must be set to 1 so that the header is consistent with the results written on the file.

The command is primarily intended for use in a top-down substructuring analysis, where the full model is resumed and the results data read from the [use pass](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/an9Auq1d6ldm.html#advobsl5jla062999) results file ( [[set|SET]] ), and subsequently from all substructure [expansion pass](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/axcAuq367ldm.html#adv5note4jla062999) results files ( [[append|APPEND]] ). The full set of data in memory can then be written out via the **RESWRITE** command to create a complete results file (as though you had run a nonsubstructured analysis).

The **RESWRITE** command can also be used to write a global results file for a distributed-memory parallel ( DMP ) solution. This should only be necessary if the [[rescombine|RESCOMBINE]] command was used to combine results from local results files into the database. The **RESWRITE** command can then be used to write the combined results into a new results file. This new results file will essentially contain the current set of results data for the entire (that is, global) model.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RESWRITE.html
