---
apdl: "SSTIF"
method: sstif
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.sstif
generated: 2026-08-22
tags: [mapdl-command]
---

# SSTIF

PyMAPDL: `mapdl.sstif(key='', **kwargs)`

Activates stress stiffness effects in a nonlinear analysis.

## Parameters

**key**

Stress stiffening key:

- `OFF` - No stress stiffening is included (default unless [[nlgeom|NLGEOM]],ON).
- `ON` - Stress stiffening is included (default if [[nlgeom|NLGEOM]],ON).

## Notes

Activates stress stiffness effects in a nonlinear analysis ( [[antype|ANTYPE]],STATIC or TRANS). (The [[pstres|PSTRES]] command also controls the generation of the stress stiffness matrix and therefore should not be used in conjunction with **SSTIF**.) If used within the solution processor, this command is valid only within the first load step.

When [[nlgeom|NLGEOM]] is ON, **SSTIF** defaults to ON. This normally forms all of the consistent tangent matrix. However, for some special nonlinear cases, this can lead to divergence caused by some elements which do not provide a complete consistent tangent (notably, elements outside the 18 `x` family). In such a case, Ansys, Inc. recommends issuing an **SSTIF**,OFF command to achieve convergence. For [current-technology elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/EL2oldnewtable.html#EL2curtechelembenefits), setting **SSTIF**,OFF when [[nlgeom|NLGEOM]] is ON has no effect (because stress stiffness effects are always included).

This command is also valid in PREP7.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SSTIF.html
