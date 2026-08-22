---
apdl: "OCLIST"
method: oclist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.ocean.Ocean.oclist
generated: 2026-08-22
tags: [mapdl-command]
---

# OCLIST

PyMAPDL: `mapdl.oclist(datatype='', zonename='', **kwargs)`

Summarizes all currently defined ocean loads.

## Parameters

**datatype**

Ocean data type to list. Valid values are BASIC, CURRENT, WAVE, ZONE, and ALL.

For `DataType` = ALL, all defined ocean loads are listed.

**zonename**: The name of an ocean zone to list. If no name is specified, all defined ocean zones are listed. Valid only when DataType = ZONE.

## Notes

The **OCLIST** command summarizes the ocean properties for all defined ocean loads in the current session.

When this command follows the [[solve|SOLVE]] command, certain waves types also list the calculated wave length.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_OCLIST.html
