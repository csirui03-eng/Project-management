---
apdl: "OSRESULT"
method: osresult
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.osresult
generated: 2026-08-22
tags: [mapdl-command]
---

# OSRESULT

PyMAPDL: `mapdl.osresult(item='', comp='', freq='', cname='', **kwargs)`

Controls the selected result data written to the database.

## Parameters

**item**: Item to output to the database. See *OSRESULT - Item and Component Labels*.

**comp**: Component of `Item` to output to the database. See *OSRESULT - Item and Component Labels*.

**freq**

Frequency to output to the database.

- `n` - Writes every `n` th and last substep of each load step.
- `-n` - Writes up to `n` equally spaced substeps of each load step.
- `ALL` - Writes every substep.
- `LAST` - Writes the last substep of each load step (default).

**cname**: The name of an element component ( [[cm|CM]] ) defining the set of elements for which this specification is active. If not specified, the set is all elements.

## Notes

**OSRESULT** controls output to the results database for the selected result defined by the item and component combination. The command activates output of the selected result for the specified substeps and elements. Multiple commands for the same result are cumulative. No selected results are written to the database unless specified via an **OSRESULT** command.

**OSRESULT**,ERASE deletes the existing output specifications.

**OSRESULT**,STATUS lists the current set of selected result specifications.

The output of selected results is valid for static ( [[antype|ANTYPE]],STATIC) and transient ( [[antype|ANTYPE]],TRANS) analysis types.

To specify other results to output to the database, see [[outres|OUTRES]].

Element quantities specified via [[outres|OUTRES]] can be redundant to those specified via **OSRESULT**. Avoid specifying redundant quantities, as they are stored and processed separately.

This command is also valid in PREP7.

### OSRESULT - Item and Component Labels

**Component Name Method**

| **Item** | **Comp** | **Description** |
|----|----|----|
| ERASE | \- | Erases all selected result output specifications. |
| STATUS | \- | Lists the current set of selected result output specifications. |
| SVAR | 1,2,3,..., `N` | State variable number. |
| FLD | UF01, UF02,..., UF09 | User-defined field variables |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_OSRESULT.html
