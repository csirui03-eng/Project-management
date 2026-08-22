---
apdl: "TBEO"
method: tbeo
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.tbeo
generated: 2026-08-22
tags: [mapdl-command]
---

# TBEO

PyMAPDL: `mapdl.tbeo(par='', value='', **kwargs)`

Sets special options or parameters for material data tables.

## Parameters

**par**

Parameter name:

- `CAPCREEPREG` - Available for the viscoplasticity/creep model ( [[tb|TB]], CREEP ), allows two creep models to be specified via the same material ID when used with the Extended Drucker-Prager model ( [[tb|TB]], EDP ).
- `FDCS` - Coordinate system to use with location (XCOR, YCOR, ZCOR) or displacement (UX, UY, UZ) field variables.
- `NEGSLOPE` - Controls whether negative tangent slopes of the stress-strain curve are allowed for multilinear [kinematic](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) or [isotropic](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#) hardening in a [rate-independent plasticity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/amp8sq21dldm.html#sintering) analysis.

**value**

Parameter value:

When `Par` = CAPCREEPREG -

- `SHEA` - Use the shear stress-state creep model with the Extended Drucker-Prager model.
- `COMP` - Use the compaction stress-state creep model with the Extended Drucker-Prager model.

When `Par` = FDCS -

- Any predefined, user-defined, or custom ( [[local|LOCAL]] or [[cs|CS]] ) Cartesian coordinate system number.

When `Par` = NEGSLOPE -

- `0` - Error-trap negative tangent slopes of the stress-strain curve (default).
- `1` - Allow negative tangent slopes of the stress-strain curve.

## Notes

Issue the **TBEO** command after activating the material data table ( [[tb|TB]] ) but before defining data for the table ( [[tbdata|TBDATA]] ) or a point on a nonlinear data curve ( [[tbpt|TBPT]] ).

If the defined material data table has subtables, issue the **TBEO** command for each desired subtable.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TBEO.html
