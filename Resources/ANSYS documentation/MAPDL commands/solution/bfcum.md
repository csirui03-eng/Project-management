---
apdl: "BFCUM"
method: bfcum
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_body_loads.FeBodyLoads.bfcum
generated: 2026-08-22
tags: [mapdl-command]
---

# BFCUM

PyMAPDL: `mapdl.bfcum(lab='', oper='', fact='', tbase='', **kwargs)`

Specifies that nodal body-force loads are to be accumulated.

**Command default:**

Replace previous values.

## Parameters

**lab**

Valid body load label. If ALL, use all appropriate labels.

(table not available in the PyMAPDL source, see the Ansys help page)

**oper**

Accumulation key:

- `REPL` - Subsequent values replace the previous values (default).
- `ADD` - Subsequent values are added to the previous values.
- `IGNO` - Subsequent values are ignored.

**fact**: Scale factor for the nodal body load values. Zero (or blank) defaults to 1.0. Use a small number for a zero scale factor. The scale factor is not applied to body load phase angles.

**tbase**

Used (only with `Lab` = TEMP) to calculate the temperature used in the add or replace operation (see `Oper` ) as:

Temperature = `TBASE` + `FACT` \* ( `T` - `TBASE` )

where `T` is the temperature specified on subsequent [[bf|BF]] commands. `TBASE` defaults to zero.

## Notes

Allows repeated nodal body-force loads to be replaced, added, or ignored. Nodal body loads are applied with the [[bf|BF]] command. Issue the [[bflist|BFLIST]] command to list the nodal body loads. The operations occur when the next body loads are defined. For example, issuing the [[bf|BF]] command with a temperature of 250 after a previous [[bf|BF]] command with a temperature of 200 causes the new value of the temperature to be 450 with the add operation, 250 with the replace operation, or 200 with the ignore operation. A scale factor is also available to multiply the next value before the add or replace operation. A scale factor of 2.0 with the previous "add" example results in a temperature of 700. The scale factor is applied even if no previous values exist. Issue **BFCUM**,STAT to show the current label, operation, and scale factors. Solid model boundary conditions are not affected by this command, but boundary conditions on the FE model are affected. FE boundary conditions may still be overwritten by existing solid model boundary conditions if a subsequent boundary condition transfer occurs.

**BFCUM** does not work for tabular boundary conditions.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFCUM.html
