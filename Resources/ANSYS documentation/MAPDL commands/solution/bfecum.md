---
apdl: "BFECUM"
method: bfecum
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_body_loads.FeBodyLoads.bfecum
generated: 2026-08-22
tags: [mapdl-command]
---

# BFECUM

PyMAPDL: `mapdl.bfecum(lab='', oper='', fact='', tbase='', **kwargs)`

Specifies whether to ignore subsequent element body force loads.

**Command default:**

Replace previous values.

## Parameters

**lab**

Valid body load label. If ALL, use all appropriate labels.

(table not available in the PyMAPDL source, see the Ansys help page)

**oper**

Replace or ignore key:

- `REPL` - Subsequent values replace the previous values (default).
- `IGNO` - Subsequent values are ignored.

**fact**: Scale factor for the element body load values. Zero (or blank) defaults to 1.0. Use a small number for a zero scale factor. The scale factor is not applied to body load phase angles.

**tbase**

Used (only with `Lab` = TEMP) to calculate the temperature used in the add or replace operation (see `Oper` ) as:

Temperature = `TBASE` + `FACT` \* ( `T` - `TBASE` )

where `T` is the temperature specified on subsequent [[bfe|BFE]] commands. `TBASE` defaults to zero.

## Notes

Allows repeated element body-force loads to be replaced or ignored. Element body loads are applied with the [[bfe|BFE]] command. Issue the [[bfelist|BFELIST]] command to list the element body loads. The operations occur when the next body loads are defined. For example, issuing the [[bfe|BFE]] command with a temperature value of 25 after a previous [[bfe|BFE]] command with a temperature value of 20 causes the new value of that temperature to be 25 with the replace operation, or 20 with the ignore operation. A scale factor is also available to multiply the next value before the replace operation. A scale factor of 2.0 with the previous "replace" example results in a temperature of 50. The scale factor is applied even if no previous values exist. Issue **BFECUM**,STAT to show the current label, operation, and scale factors.

**BFECUM** does not work for tabular boundary conditions.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFECUM.html
