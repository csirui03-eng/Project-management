---
apdl: "*VCUM"
method: vcum
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.vcum
generated: 2026-08-22
tags: [mapdl-command]
---

# *VCUM

PyMAPDL: `mapdl.vcum(key='', **kwargs)`

Allows array parameter results to add to existing results.

## Parameters

**key**

Accumulation key:

- `0` - Overwrite results.
- `1` - Add results to the current value of the results parameter.

## Notes

Allows results from certain **\*V** `XX` and **\*M** `XX` operations to overwrite or add to existing results. The cumulative operation is of the form: ParR = ParR + ParR(Previous)

The cumulative setting is reset to the default (overwrite) after each **\*V** `XX` or **\*M** `XX` operation. Use [[vstat|*VSTAT]] to list settings.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VCUM.html
