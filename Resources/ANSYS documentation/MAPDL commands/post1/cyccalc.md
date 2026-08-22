---
apdl: "CYCCALC"
method: cyccalc
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.cyccalc
generated: 2026-08-22
tags: [mapdl-command]
---

# CYCCALC

PyMAPDL: `mapdl.cyccalc(fileprefix='', fileformat='', separator='', **kwargs)`

Calculates results from a cyclic harmonic mode-superposition analysis using the specifications defined by [[cycspec|CYCSPEC]].

**Command default:**

Write the result tables to the output file.

## Parameters

**fileprefix**: Each result table (corresponding to each [[cycspec|CYCSPEC]] specification) is written to a file beginning with `FilePrefix`. If blank (default), the result tables are written to the output file.

**fileformat**

If `FilePrefix` is specified, then use `FileFormat` to specify the format of the file to be written:

- `FORM` - Formatted file (default)
- `CSV` - Comma-separated value file

**separator**

If `FileFormat` is CSV, use `Separator` to specify the field separator:

- `COMMA` - Use a comma () as the field separator (default)
- `COLON` - Use a colon (:) as the field separator
- `DOT` - Use a period (.) as the field separator

## Notes

**CYCCALC** loops through the specification given by [[cycspec|CYCSPEC]] and computes the requested outputs. The outputs are given in a table format, with the rows corresponding to each frequency solution from the harmonic analysis, and the columns corresponding to each sector. The table entries are the maximum value of the specified quantity at the specified location in the sector. In addition, columns containing the maximum value at the frequency, the sector in which it occurs, and the node in the sector at which it occurs are output.

If `FilePrefix` is specified, a file is created for each output table with the name `FilePrefix_node_type.ext`, where `node` is the node number or component name, `type` is the item/component requested, and the file extension `.ext` is either `.txt` or `.csv`, depending on `FileFormat`.

A [[set|SET]] command must precede the **CYCCALC** command.

The **CYCCALC** results are based on the currently active [[rsys|RSYS]], [[shell|SHELL]], [[layer|LAYER]], and [[avprin|AVPRIN]] settings.

The **CYCCALC** command only supports matched nodes. For more details on matching cyclic edge node pairs see [Edge Component Pairs](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycedgecomp.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYCCALC.html
