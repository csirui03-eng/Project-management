---
apdl: "*VFACT"
method: vfact
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.vfact
generated: 2026-08-22
tags: [mapdl-command]
---

# *VFACT

PyMAPDL: `mapdl.vfact(factr='', fact1='', fact2='', fact3='', **kwargs)`

Applies a scale factor to array parameters.

## Parameters

**factr**: Scale factor applied to results (ParR) parameter. Defaults to 1.0.

**fact1**: Scale factor applied to first parameter (Par1 or ParI). Defaults to 1.0.

**fact2**: Scale factor applied to second parameter (Par2 or ParJ). Defaults to 1.0.

**fact3**: Scale factor applied to third parameter (Par3 or ParK). Defaults to 1.0.

## Notes

### Argument descriptions

- `factr : str` - Scale factor applied to results (ParR) parameter. Defaults to 1.0.
- `fact1 : str` - Scale factor applied to first parameter (Par1 or ParI). Defaults to 1.0.
- `fact2 : str` - Scale factor applied to second parameter (Par2 or ParJ). Defaults to 1.0.
- `fact3 : str` - Scale factor applied to third parameter (Par3 or ParK). Defaults to 1.0.

Applies a scale factor to parameters used in certain **\*V** `XX` and **\*M** `XX` operations. Typical scale factor applications are of the form: ParR = `FACTR` \*f( `FACT1` \*Par1)

> or
>
> ParR = `FACTR` \*(( `FACT1` \*Par1) o ( `FACT2` \*Par2))

The factors are applied to each input parameter value before the operation and to the result value after the operation. The scale factor settings are reset to the default (1.0) after each **\*V** `XX` or **\*M** `XX` operation. Use [[vstat|*VSTAT]] to list settings.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VFACT.html
