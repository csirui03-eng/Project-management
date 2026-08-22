---
apdl: "*VABS"
method: vabs
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.vabs
generated: 2026-08-22
tags: [mapdl-command]
---

# *VABS

PyMAPDL: `mapdl.vabs(kabsr='', kabs1='', kabs2='', kabs3='', **kwargs)`

Applies the absolute value function to array parameters.

## Parameters

**kabsr**

Absolute value of results parameter:

- `0` - Do not take absolute value of results parameter (ParR).
- `1` - Take absolute value.

**kabs1**

Absolute value of first parameter:

- `0` - Do not take absolute value of first parameter (Par1 or ParI).
- `1` - Take absolute value.

**kabs2**

Absolute value of second parameter:

- `0` - Do not take absolute value of second parameter (Par2 or ParJ).
- `1` - Take absolute value.

**kabs3**

Absolute value of third parameter:

- `0` - Do not take absolute value of third parameter (Par3 or ParK).
- `1` - Take absolute value.

## Notes

Applies an absolute value to parameters used in certain **\*V** `XX` and **\*M** `XX` operations. Typical absolute value applications are of the form: ParR = \|f(\|Par1\|)\|

> or
>
> ParR = \|(\|Par1\| o \|Par2\|)\|

The absolute values are applied to each input parameter value before the operation and to the result value after the operation. Absolute values are applied before the scale factors so that negative scale factors may be used. The absolute value settings are reset to the default (no absolute value) after each **\*V** `XX` or **\*M** `XX` operation. Use [[vstat|*VSTAT]] to list settings.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VABS.html
