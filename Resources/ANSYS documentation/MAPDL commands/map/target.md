---
apdl: "TARGET"
method: target
group: map
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.map.pressure_mapping.PressureMapping.target
generated: 2026-08-22
tags: [mapdl-command]
---

# TARGET

PyMAPDL: `mapdl.target(nlist='', **kwargs)`

Specifies the target nodes for mapping pressures onto surface effect elements.

## Parameters

**nlist**: Nodes defining the surface upon which the pressures will be mapped. Use the label ALL or specify a nodal component name. If ALL, all selected nodes ( [[nsel|NSEL]] ) are used (default). Individual nodes may not be entered.

## Notes

The node list specified by `Nlist` must contain a sufficient number of nodes to define an element surface. The surface must be meshed ( [[esurf|ESURF]] command) with `SURF154` elements prior to issuing this command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TARGET.html
