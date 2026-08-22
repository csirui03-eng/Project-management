---
apdl: "VERIFY"
method: verify
group: misc
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.misc.misc.Misc.verify
generated: 2026-08-22
tags: [mapdl-command]
---

# VERIFY

PyMAPDL: `mapdl.verify(case='', level='', **kwargs)`

Enter the verification run mode.

> [!NOTE]
> This command is only valid at the `/BEGIN` level, obtained with `mapdl.finish()`.

## Parameters

**case**: Optional title of the verification manual file. Also accepts `'OFF'` to disable the verification run mode.

**level**: Verification level ranging from 1 to 6 defaulting to 4.

## Returns

`str`: Command output.

## Examples

Enter the verification routine with the default option.

``` python
>>> mapdl.finish()
>>> mapdl.verify('VM1')
'*** VERIFICATION RUN - CASE VM1                              ***  OPTION=  4'
```
