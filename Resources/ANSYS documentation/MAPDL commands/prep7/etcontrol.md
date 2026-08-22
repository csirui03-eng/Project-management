---
apdl: "ETCONTROL"
method: etcontrol
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.element_type.ElementType.etcontrol
generated: 2026-08-22
tags: [mapdl-command]
---

# ETCONTROL

PyMAPDL: `mapdl.etcontrol(eltech='', eldegene='', **kwargs)`

Control the element technologies used in element formulation (for applicable elements).

## Parameters

**eltech**

Element technology control:

- `SUGGESTION` - The program offers a suggestion for the best element technology before solving. If necessary, mixed u-P (KEYOPT(6)) is also included and reset. This behavior is the default.
- `SET` - The program informs you of the best settings and resets any applicable KEYOPT settings automatically. This action overrides any previous manual settings.
- `OFF` - Deactivates automatic selection of element technology. No suggestions are issued, and no automatic resetting occurs.

**eldegene**

Element degenerated shape control:

- `ON` - If element shapes are degenerated, the degenerated shape function is employed and enhanced strain, simplified enhanced strain, and B-bar formulations are turned off (default).
- `OFF` - If element shapes are degenerated, regular shape functions are still used, and the specified element technologies (for example, enhanced strain, B-bar, uniform reduced integration) are still used.

## Notes

This command is valid for elements `SHELL181`, `PLANE182`, `PLANE183`, `SOLID185`, `SOLID186`, `SOLID187`, `BEAM188`, `BEAM189`, `SHELL208`, `SHELL209`, `PLANE222`, `PLANE223`, `SOLID225`, `SOLID226`, `SOLID227`, `REINF264`, `SOLID272`, `SOLID273`, `SHELL281`, `SOLID285`, `PIPE288`, `PIPE289`, `ELBOW290`.

For more information, see [Automatic Selection of Element Technologies and Formulations](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_AutoSelectElems.html#EL2recCriteriaNonLin-3)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ETCONTROL.html
