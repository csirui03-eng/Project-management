---
apdl: "MAP"
method: map
group: map
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.map.pressure_mapping.PressureMapping.map
generated: 2026-08-22
tags: [mapdl-command]
---

# MAP

PyMAPDL: `mapdl.map(kdim='', kout='', limit='', **kwargs)`

Maps pressures from source points to target surface elements.

## Parameters

**kdim**

Interpolation key:

- `0 or 2` - Interpolation is done on a surface (default).
- `3` - Interpolation is done within a volume. This option is useful if the supplied source data is volumetric field data rather than surface data.

**kout**

Key to control how pressure is applied when a target node is outside of the source region:

- `0` - Use the pressure(s) of the nearest source point for target nodes outside of the region (default).
- `1` - Set pressures outside of the region to zero.

**limit**: Number of nearby points considered for interpolation. The minimum is 5; the default is 20. Lower values reduce processing time. However, some distorted or irregular meshes will require a higher `LIMIT` value to find the points encompassing the target node in order to define the region for interpolation.

## Notes

Maps pressures from source points to target surface elements.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MAP.html
