---
apdl: "GMFACE"
method: gmface
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.gmface
generated: 2026-08-22
tags: [mapdl-command]
---

# GMFACE

PyMAPDL: `mapdl.gmface(lab='', n='', **kwargs)`

Specifies the facet representation used to form solid models.

## Parameters

**lab**

Valid Labels:

- `FINE` - Value that determines how coarse the facets will be.

**n**: An integer value between one (small) and ten (large) that determines the tolerances that will be applied to the creation of arcs and surfaces. Ten will create many facets, which may in turn cause Mechanical APDL to run very slowly. One will create fewer facets, which may in turn cause larger tolerance errors.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GMFACE.html
