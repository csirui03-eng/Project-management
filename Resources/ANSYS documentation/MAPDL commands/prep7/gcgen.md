---
apdl: "GCGEN"
method: gcgen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.gcgen
generated: 2026-08-22
tags: [mapdl-command]
---

# GCGEN

PyMAPDL: `mapdl.gcgen(option='', featureangle='', edgekey='', splitkey='', selopt='', **kwargs)`

Creates contact elements for general contact.

## Parameters

**option**

Option to be performed.

- `NEW` - Create a new general contact definition. This option removes all existing general contact elements and generates new elements with new section IDs. Any existing [[gcdef|GCDEF]] specifications, general contact [[sectype|SECTYPE]] / [[secdata|SECDATA]] data, and general contact element types are also removed. If no general contact elements or data exist, this option behaves the same as `Option` = UPDATE.
- `UPDATE` - Generate general contact elements on newly added (or selected) base elements. Newly generated contact elements are assigned new Section IDs. Existing general contact elements remain with their previously assigned section IDs and element attributes. Existing [[gcdef|GCDEF]] and [[sectype|SECTYPE]] / [[secdata|SECDATA]] general contact data are respected. (This is the default option.)
- `DELETE` - Remove all existing general contact elements. Existing [[gcdef|GCDEF]] specifications, general contact [[sectype|SECTYPE]] / [[secdata|SECDATA]] data, and general contact element types are also removed.
- `SELECT` - Select all existing general contact elements.

**featureangle**: Angle tolerance for determining feature edges ( `EdgeKEY` ) and general surfaces ( `SplitKey` ). Default = 42 degrees.

**edgekey**

Key that controls creation of general contact line and vertex elements ( `CONTA177`, `CONTA175` ) on base elements. Line elements are overlaid on feature edges of 3D deformable bodies and on perimeter edges of 3D shell structures; vertex elements are overlaid on convex corners of deformable bodies and shell structures (2D or 3D), and on endpoints of 3D beam structures. See Understanding `FeatureANGLE` for an explanation of the feature edge criteria.

- `0` - Exclude all edges and vertices (default).
- `1` - Include `CONTA177` elements on feature edges only.
- `2` - Include `CONTA177` elements on shell perimeter edges only.
- `3` - Include `CONTA177` elements on feature edges and shell perimeter edges.
- `4` - Include `CONTA177` elements on feature edges and shell perimeter edges, and `CONTA175` elements on vertices.
- `5` - Include `CONTA175` elements on vertices only.

`EdgeKey` \> 0 is intended to add extra contact constraint between an edge or vertex of one surface and other 3D surfaces. Both edge and vertex contact always use the penalty method and only include structural degrees of freedom (UX, UY, UZ).

**GCGEN** always creates `CONTA177` elements on base beam elements, regardless of the `EdgeKEY` setting.

**splitkey**

Key that controls how section IDs and contact element type IDs are assigned to surfaces.

- `SPLIT` - Assign a different section ID and contact element type ID for every general surface of the selected base elements (default). See Understanding `FeatureANGLE` for an explanation of the split criteria. Different section IDs are assigned to the top and bottom surfaces of 2D shell and 3D shell bodies. This allows different [[gcdef|GCDEF]] specifications for different portions of the assembly.
- `PART` - Assign a different section ID and contact element type ID for every general surface which covers a physical part. Compared to the SPLIT option, this option produces fewer unique section IDs, which can make it easier to specify interactions via [[gcdef|GCDEF]]. However, it may also result in a less accurate and/or less efficient solution.

**selopt**

Key that controls which base elements are considered for general contact.

- `ATTACH` - Use a recursive adjacency selection to obtain complete physical parts (default). This selection starts from the selected base elements, progressively adding elements adjacent to the faces of selected elements until the edge of a part is reached. Then general contact elements are generated.
- `SELECT` - Use only the initially selected base elements to generate general contact elements.

## Notes

**GCGEN** creates general contact elements on the exterior faces of selected base elements. The base elements can be 2D or 3D solids, 3D beams, 2D shells (top and bottom), or 3D shells (top and bottom). The contact element types can be `CONTA172`, `CONTA174`, `CONTA175`, and/or `CONTA177`, depending upon the types of base elements in the model and the specified **GCGEN** options. General contact elements are identified by a real constant ID equal to zero.

You can control contact interactions between specific general contact surfaces that could potentially be in contact by using the [[gcdef|GCDEF]] command. See [General Contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_toolsgencont.html)

****Understanding FeatureANGLE****

The exterior facets of the selected base solid and shell elements are divided into subsets based on the angle between the normals of neighboring faces. On a flat or smooth surface, adjacent exterior element faces have normals that are parallel or nearly parallel; that is, the angle between the adjacent normals is near zero degrees.

When the angle between the normals of two adjacent faces is greater than `FeatureANGLE`, the two faces are considered to be on two separate surfaces ( `SplitKey` = SPLIT). The edge between the faces may be convex or concave. A convex (or outside) edge is considered to be a feature edge and may be affected by the `EdgeKEY` setting. For more information, see [Feature Angle ( FeatureANGLE)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctec_generategc.html#gencontsurf)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GCGEN.html
