---
apdl: "SPCNOD"
method: spcnod
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.radiosity.Radiosity.spcnod
generated: 2026-08-22
tags: [mapdl-command]
---

# SPCNOD

PyMAPDL: `mapdl.spcnod(encl='', node='', **kwargs)`

Defines a space node for radiation using the Radiosity method.

## Parameters

**encl**: Radiating surface enclosure number. Defaults to 1. If ENCL = STAT, the command lists all enclosure space nodes. If ENCL = DELE, the command deletes all enclosure space nodes.

**node**: Node defined to be the space node.

## Notes

For open systems, an enclosure may radiate to a space node ( `NODE` ).

Open systems may be characterized by one or more enclosures ( `ENCL` ). Each enclosure may radiate to a different space node ( `NODE` ).

For a space node that is not part of the finite element model, specify the temperature using the [[d|D]] command. For the first load step, the space node temperature ramps from the uniform temperature specified by the [[tunif|TUNIF]] command to the temperature specified by the [[d|D]] command. For subsequent load steps, it ramps from the previous value of the space node temperature. For intermediate load steps, use the **SPCNOD**,DELETE command and specify the space node temperature again to ramp from the uniform temperature.

For a space node that is part of the finite element model, the temperature is that calculated during the finite element solution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPCNOD.html
