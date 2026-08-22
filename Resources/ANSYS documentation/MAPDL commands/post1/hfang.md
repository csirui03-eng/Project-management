---
apdl: "HFANG"
method: hfang
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.hfang
generated: 2026-08-22
tags: [mapdl-command]
---

# HFANG

PyMAPDL: `mapdl.hfang(lab='', phi1='', phi2='', theta1='', theta2='', **kwargs)`

Defines or displays spatial angles of a spherical radiation surface for sound radiation parameter calculations.

## Parameters

**lab**

Spatial angle label.

- `ANGLE` - Define spatial angles (default).
- `STATE` - Display spatial angles. `PHI1`, `PHI2`, `THETA1`, and `THETA2` are ignored.

**phi1**, **phi2**: Starting and ending ϕ angles (degrees) in the spherical coordinate system. `PHI1` defaults to 0 and `PHI2` defaults to 360.

**theta1**, **theta2**: Starting and ending θ angles (degrees) in the spherical coordinate system. `THETA1` defaults to 0 and `THETA2` defaults to 180.

## Notes

Defines or displays spatial angles of a spherical radiation surface.

Use this command only with [[plfar|PLFAR]], `Lab` = PRES, or [[prfar|PRFAR]], `Lab` = PRES.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HFANG.html
