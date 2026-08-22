---
apdl: "BEND"
method: bend
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.piping.Piping.bend
generated: 2026-08-22
tags: [mapdl-command]
---

# BEND

PyMAPDL: `mapdl.bend(nel1='', nel2='', rad='', ndiv='', estrt='', einc='', **kwargs)`

Defines a bend in a piping run.

## Parameters

**nel1**, **nel2**: Element numbers of the two intersecting straight pipes. Defaults to the last two straight pipe elements nearest the intersection of the last two runs.

**rad**: Bend radius. If LR, use long radius standard (1.5 x nominal diameter) (default). If SR, use short radius standard (1.0 x nominal diameter).

**ndiv**: Number of divisions (elements) along bend (defaults to 2). A node is generated at the end of each division.

**estrt**: Number to be assigned to first element of bend (defaults to MAXEL + 1).

**einc**: Element number increment (defaults to 1).

## Notes

Defines a bend of curved (elbow) pipe elements (PIPE18) in place of the intersection of two previously defined straight pipe elements (RUN). Two new nodes are generated at the ends of the bend (at the tangency points). A node is also generated at the center of curvature point. The two straight pipes are automatically "shortened" to meet the ends of the bend. The bend specifications and loadings are taken from the corresponding two straight pipes. The flexibility factors are calculated from the internal pressure and EX (evaluated at TAVE) based on the current PPRES and PTEMP command specifications when the element is generated.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BEND.html
