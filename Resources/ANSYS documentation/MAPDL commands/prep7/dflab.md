---
apdl: "/DFLAB"
method: dflab
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.dflab
generated: 2026-08-22
tags: [mapdl-command]
---

# /DFLAB

PyMAPDL: `mapdl.dflab(dof='', displab='', forcelab='', **kwargs)`

Changes degree-of-freedom labels for user custom elements.

## Parameters

**dof**

Number between 1 and 32 indicating which degree of freedom is to have its labels changed. For a list of these quantities, see the degree-of-freedom table in the `echprm.inc` file. The first few quantities follow:

- 1 = UX,FX
- 2 = UY,FY
- 3 = UZ,FZ
- 4 = ROTX,MX

**displab**: New label (four-character maximum) for the displacement label. The prior label is no longer valid.

**forcelab**: New label (four-character maximum) for the force label for this degree of freedom. The prior label is no longer valid.

## Notes

### Argument descriptions

\* `dof : str` - Number between 1 and 32 indicating which degree of freedom is to have its labels changed. For a list of these quantities, see the degree-of-freedom table in the `echprm.inc` file. The first few quantities follow:

> - 1 = UX,FX
> - 2 = UY,FY
> - 3 = UZ,FZ
> - 4 = ROTX,MX

- `displab : str` - New label (four-character maximum) for the displacement label. The prior label is no longer valid.
- `forcelab : str` - New label (four-character maximum) for the force label for this degree of freedom. The prior label is no longer valid.

The **/DFLAB** command is rarely used. Use it if you are writing a custom element and want to use degrees of freedom that are not part of the standard element set.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DFLAB.html
