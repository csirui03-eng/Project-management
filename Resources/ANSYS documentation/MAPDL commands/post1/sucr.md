---
apdl: "SUCR"
method: sucr
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.surface_operations.SurfaceOperations.sucr
generated: 2026-08-22
tags: [mapdl-command]
---

# SUCR

PyMAPDL: `mapdl.sucr(surfname='', surftype='', nrefine='', radius='', tolout='', **kwargs)`

Create a surface.

## Parameters

**surfname**: Eight character surface name.

**surftype**

Surface type.

- `CPLANE` - Surface is defined by the cutting plane in window one (controlled by the working plane (/CPLANE,1), NOT the view settings (/CPLANE,0)).
- `SPHERE` - Surface is defined by a spherical surface centered about the working plane origin.
- `INFC` - Surface is defined by a cylindrical surface centered about the working plane origin and extending indefinitely in the positive and negative Z directions.

**nrefine**

Refinement level.

- `For SurfType = CPLANE` - The refinement level of the surface mesh. This will be an integer between 0 and 3 (default = 0). See Notes below.
- `For SurfType = SPHERE` - The number of divisions along a 90° arc (minimum = 9). The default is 9.
- `For SurfType = INFC` - The number of divisions along a 90° arc (minimum = 9). The default is 9.

**radius**: Appropriate radius value (for INFC or SPHERE).

**tolout**: Tolerance value for inclusion of element facets within a prescribed volume. (for INFC)

## Notes

This command creates a new surface and stores the following data for that surface:

- GCX, GCY, GCZ - global Cartesian coordinates at each point on the surface.
- NORMX, NORMY, NORMZ - components of the unit normal at each point on the surface.
- DA - the contributory area of each point.

For `SurfType` = CPLANE, `nRefine` refers to the number of points that define the surface. An `nRefine` value of zero is used for points where the element face intersects the cutting plane.

If `SurfType` = CPLANE and `nRefine` = 0, the points reside at the section cuts where the element intersects the cutting plane. Increasing `nRefine` from 0 to 1 will subdivide each surface facet into 4 subfacets, and increase the number of points at which results can be interpolated.

For `SurfType` = CPLANE, the setting from the [[efacet|/EFACET]] command will affect the creation of surface facets and the quality of the fit of the surface in the model. **SUCR** employs geometry data from PowerGraphics to aid in determining where the surface intersects the model. If [[efacet|/EFACET]],1 is in effect when the **SUCR** command is issued, then the curvature of high order elements (that is, elements with midside nodes) will be ignored. If your model contains high order elements, you can see a better fit for your surface if /EFACET,2 is in effect when the **SUCR** command is issued. Currently, the **SUCR** command interprets [[efacet|/EFACET]],4 to mean [[efacet|/EFACET]],2.

For `SurfType` = INFC, a default tolerance of 0.01 will be applied to include the vertices of any facets that fall out of the cylinder definition. This tolerance increases the facet size by one percent to check for inclusion. Excluding facets under such a small tolerance may yield unacceptable (aesthetically) results. Increasing the tolerance by a larger amount (0.1 or 10%) will sometimes yield smother edges along the surface you create.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SUCR.html
