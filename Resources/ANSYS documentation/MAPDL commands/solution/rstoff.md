---
apdl: "RSTOFF"
method: rstoff
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.rstoff
generated: 2026-08-22
tags: [mapdl-command]
---

# RSTOFF

PyMAPDL: `mapdl.rstoff(lab='', offset='', **kwargs)`

Offsets node or element IDs in the FE geometry record.

**Command default:**

Issuing the **RSTOFF** command with no specified argument values applies no offsets.

## Parameters

**lab**

The offset type:

- `NODE` - Offset the node IDs.
- `ELEM` - Offset the element IDs.

**offset**: A positive integer value specifying the offset value to apply. The value must be greater than the number of nodes or elements in the existing superelement results file.

## Notes

The **RSTOFF** command offsets node or element IDs in the FE geometry record saved in the `.rst` results file. Use the command when expanding superelements in a bottom-up substructuring analysis (where each superelement is generated individually in a [generation pass](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/advcmssuperelem.html#usingcms_elemcalc), and all superelements are assembled together in the [use pass](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/an9Auq1d6ldm.html#advobsl5jla062999) ).

With appropriate offsets, you can write results files with unique node or element IDs and thus display the entire model even if the original superelements have overlapping element or node ID sets. (Such results files are incompatible with the `.db` database file saved at the generation pass.)

The offset that you specify is based on the original superelement node or element numbering, rather than on any offset specified via a [[sesymm|SESYMM]] or [[setran|SETRAN]] command. When issuing an **RSTOFF** command, avoid specifying an offset that creates conflicting node or element numbers for a superelement generated via a [[sesymm|SESYMM]] or [[setran|SETRAN]] command.

If you issue the command to set non-zero offsets for node or element IDs, you must bring the geometry into the database via the [[set|SET]] command so that Mechanical APDL can display the results. Specify appropriate offsets to avoid overlapping node or element IDs with other superelement results files.

The command is valid only in the first load step of a [superelement expansion pass](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/axcAuq367ldm.html#adv5note4jla062999).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RSTOFF.html
