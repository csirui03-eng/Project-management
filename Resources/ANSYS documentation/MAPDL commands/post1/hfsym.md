---
apdl: "HFSYM"
method: hfsym
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.hfsym
generated: 2026-08-22
tags: [mapdl-command]
---

# HFSYM

PyMAPDL: `mapdl.hfsym(kcn='', xkey='', ykey='', zkey='', **kwargs)`

Indicates the presence of symmetry planes for the computation of acoustic fields in the near and far field domains (beyond the finite element region).

## Parameters

**kcn**: Coordinate system reference number. `KCN` may be 0 (Cartesian), or any previously defined local Cartesian coordinate system number (\>10). Defaults to 0.

**xkey**

Key for acoustic field boundary condition, as prescribed for the solution, corresponding to the x = constant plane:

- `None` - No sound soft or sound hard boundary conditions (default).
- `SSB` - Sound soft boundary (pressure = 0).
- `SHB` - Sound hard boundary (normal velocity = 0).

**ykey**

Key for acoustic field boundary condition, as prescribed for the solution, corresponding to the y = constant plane:

- `None` - No sound soft or sound hard boundary conditions (default).
- `SSB` - Sound soft boundary (pressure = 0).
- `SHB` - Sound hard boundary (normal velocity = 0).

**zkey**

Key for acoustic field boundary condition, as prescribed for the solution, corresponding to the z = constant plane:

- `None` - No sound soft or sound hard boundary conditions (default).
- `SSB` - Sound soft boundary (pressure = 0).
- `SHB` - Sound hard boundary (normal velocity = 0).

## Notes

**HFSYM** uses the image principle to indicate symmetry planes (x, y, or z = constant plane) for acoustic field computations outside the modeled domain. A sound hard boundary condition must be indicated even though it occurs as a natural boundary condition.

No menu paths are available for acoustic applications.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HFSYM.html
