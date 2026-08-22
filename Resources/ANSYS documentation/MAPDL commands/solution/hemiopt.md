---
apdl: "HEMIOPT"
method: hemiopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.radiosity.Radiosity.hemiopt
generated: 2026-08-22
tags: [mapdl-command]
---

# HEMIOPT

PyMAPDL: `mapdl.hemiopt(hres='', tolerance='', **kwargs)`

Specifies options for Hemicube view factor calculation.

## Parameters

**hres**: Hemicube resolution. Increase value to increase the accuracy of the view factor calculation. Defaults to 10.

**tolerance**: Tolerance value that controls whether or not facets are subdivided in view factor calculations to increase view factor accuracy. `TOLERANCE` is closely related to the spacing between facets. Defaults to 1e-6.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HEMIOPT.html
