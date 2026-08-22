---
apdl: "FGET"
method: fget
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.fget
generated: 2026-08-22
tags: [mapdl-command]
---

# FGET

PyMAPDL: `mapdl.fget(node, idf, kcmplx, pname='__tmpvar__', **kwargs)`

Get a force load from the data base.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**node**: Node number

**idf**

Pointer to the dof (1-32)

- 1 = ux
- 2 = uy
- 3 = uz
- 4 = rotx
- 5 = roty
- 6 = rotz
- 7 = ax
- 8 = ay
- 9 = az
- 10 = vx
- 11 = vy
- 12 = vz
- 13-18 = spares
- 19 = pres
- 20 = temp
- 21 = volt
- 22 = mag
- 23 = enke
- 24 = ends
- 25 = emf
- 26 = curr
- 27-32 = spares

**kcmplx**

- 0 = real
- 1 = imaginary

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`float`: Force value (high number if undefined)
