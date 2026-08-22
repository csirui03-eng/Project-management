---
apdl: "KCALC"
method: kcalc
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1._special_purpose.SpecialPurpose.kcalc
generated: 2026-08-22
tags: [mapdl-command]
---

# KCALC

PyMAPDL: `mapdl.kcalc(kplan='', mat='', kcsym='', klocpr='', **kwargs)`

Calculates stress intensity factors in fracture mechanics analyses.

## Parameters

**kplan**

Key to indicate stress state for calculation of stress intensity factors:

- `0` - Plane strain and axisymmetric condition (default).
- `1` - Plane stress condition.

**mat**: Material number used in the extrapolation (defaults to 1).

**kcsym**

Symmetry key:

- `0 or 1` - Half-crack model with symmetry boundary conditions ( [[dsym|DSYM]] \]) in the crack-tip coordinate system. K<sub>II</sub> = K<sub>III</sub> = 0. Three nodes are required on the path.
- `2` - Like 1 except with antisymmetric boundary conditions (K<sub>I</sub> = 0).
- `3` - Full-crack model (both faces). Five nodes are required on the path (one at the tip and two on each face).

**klocpr**

Local displacements print key:

- `0` - Do not print local crack-tip displacements.
- `1` - Print local displacements used in the extrapolation technique.

## Notes

Calculates the stress intensity factors (K<sub>I</sub>, K<sub>II</sub>, and K<sub>III</sub> ) associated with homogeneous isotropic linear elastic fracture mechanics.

A displacement extrapolation method is used in the calculation. (See [POST1 - Crack Analysis (KCALC)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/bob143.html#eq57266024-e263-4fd8-b9d4-5ff7d2c2411a) `KPLAN` = 1.

The program uses minor Poisson's ratio ( [[mp|MP]],NUXY) for the stress intensity factor calculation.

Issue the [[path|PATH]] and [[ppath|PPATH]] commands to define a path with the crack face nodes ( `NODE1` at the crack tip, `NODE2` and `NODE3` on one face, `NODE4` and `NODE5` on the other (optional) face).

A crack-tip coordinate system, having x parallel to the crack face (and perpendicular to the crack front) and y perpendicular to the crack face, must be the active [[rsys|RSYS]] and [[csys|CSYS]] before **KCALC** is issued.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KCALC.html
