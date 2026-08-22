---
apdl: "NUMMRG"
method: nummrg
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.database.Database.nummrg
generated: 2026-08-22
tags: [mapdl-command]
---

# NUMMRG

PyMAPDL: `mapdl.nummrg(label='', toler='', gtoler='', action='', switch='', **kwargs)`

Merges coincident or equivalently defined items.

## Parameters

**label**

Items to be merged:

- `NODE` - Nodes
- `ELEM` - Elements
- `KP` - Keypoints (will also merge lines, areas, and volumes)
- `MAT` - Materials
- `TYPE` - Element types
- `REAL` - Real constants
- `SECT` - Section types
- `CP` - Coupled sets
- `CE` - Constraint equations
- `ALL` - All items

**toler**: Range of coincidence. For `Label` = NODE and KP, defaults to 1.0E-4 (based on maximum Cartesian coordinate difference between nodes or keypoints). For `Label` = MAT, REAL, SECT, and CE, defaults to 1.0E-7 (based on difference of the values normalized by the values). Only items within range are merged. (For keypoints attached to lines, further restrictions apply. See the `GTOLER` field and Merging Solid Model Entities below.)

**gtoler**: Global solid model tolerance - used only when merging keypoints attached to lines. If specified, `GTOLER` will override the internal relative solid model tolerance. See Merging Solid Model Entities below.

**action**

Specifies whether to merge or select coincident items.

- `SELE` - Select coincident items but do not merge. `Action` = SELE is only valid for `Label` = NODE.
- `(Blank)` - Merge the coincident items (default).

**switch**

Specifies whether the lowest or highest numbered coincident item is retained after the merging operation. This option does not apply to keypoints; that is, for `Label` = KP, the lowest numbered keypoint is retained regardless of the `Switch` setting.

- `LOW` - Retain the lowest numbered coincident item after the merging operation (default).
- `HIGH` - Retain the highest numbered coincident item after the merging operation.

## Notes

The **NUMMRG** command does not change a model's geometry, only the topology.

After issuing the command, the area and volume sizes ( [[asum|ASUM]] and [[vsum|VSUM]] ) may give slightly different results. In order to obtain the same results as before, use [[facet|/FACET]], [[normal|/NORMAL]], and [[asum|ASUM]] / [[vsum|VSUM]].

The merge operation is useful for tying separate but coincident parts of a model together. If not all items are to be checked for merging, use the select commands ( [[nsel|NSEL]], [[esel|ESEL]], etc.) to select items. Only selected items are included in the merge operation for nodes, keypoints, and elements.

By default, the merge operation retains the lowest numbered coincident item. Higher numbered coincident items are deleted. Set `Switch` to HIGH to retain the highest numbered coincident item after the merging operation. Applicable related items are also checked for deleted item numbers and if found, are replaced with the retained item number. For example, if nodes are merged, element connectivities (except superelements), mesh item range associativity, coupled degrees of freedom, constraint equations, master degrees of freedom, degree of freedom constraints, nodal-force loads, nodal surface loads, and nodal body force loads are checked. Merging material numbers ( **NUMMRG**,ALL or **NUMMRG**,MAT) does not update the material number referenced:

- By temperature-dependent film coefficients as part of convection load or a temperature-dependent emissivity as part of a surface-to-surface radiation load ( [[sf|SF]], [[sfe|SFE]], [[sfl|SFL]], [[sfa|SFA]] )
- By real constants for multi-material elements

When merging tapered beam or pipe sections, the program first uses the associated end sections for merging. If the merge is successful, the program replaces the tapered section database with the end section data.

If a unique load is defined among merged nodes, the value is kept and applied to the retained node. If loads are not unique (not recommended), only the value on the lowest node (or highest if `Switch` = HIGH) is kept (except for "force" loads for which the values are summed if they are not defined via tabular boundary conditions).

The unused nodes (not recommended) in elements, couplings, constraint equations, etc. may become active after the merge operation.

> The `Action` field provides the option of visualizing the coincident items before the merging

operation.

> [!WARNING]
> When merging entities in a model that has already been meshed, the order in which you issue multiple **NUMMRG** commands is significant. To merge two adjacent meshed regions having coincident nodes and keypoints, always merge nodes ( **NUMMRG**,NODE) before merging keypoints ( **NUMMRG**,KP); otherwise, some of the nodes may lose their association with the solid model (causing other operations to fail). To prevent mesh failure, avoid multiple merging and meshing operations.

After a **NUMMRG**,NODE command executes, some nodes may be attached to more than one solid entity. As a result, subsequent attempts to transfer solid model loads to the elements may not be successful. Issue **NUMMRG**,KP to correct this problem. Do NOT issue [[vclear|VCLEAR]] before issuing **NUMMRG**,KP.

For **NUMMRG**,ELEM, elements must be identical in all aspects, including the direction of the element coordinate system.

For certain solid and shell elements, the program interprets coincident faces as internal and eliminate them. To prevent this from occurring, shrink the entities by a very small factor to delineate coincident items ( [[shrink|/SHRINK]], 0.0001) and no internal nodes, lines, areas or elements will be eliminated.

When working with solid models, you may have better success with the gluing operations ( [[aglue|AGLUE]], [[lglue|LGLUE]], [[vglue|VGLUE]] ). Please read the following information when attempting to merge solid model entities.

Gluing Operations vs. Merging Operations

Adjacent, touching regions can be joined by gluing them ( [[aglue|AGLUE]], [[lglue|LGLUE]], [[vglue|VGLUE]] ) or by merging coincident keypoints ( **NUMMRG**,KP, which also causes merging of identical lines, areas, and volumes). In many situations, either approach will work just fine. Some factors, however, may lead to a preference for one method over the other.

**Geometric Configuration**

Gluing is possible regardless of the initial alignment or offset of the input entities. Keypoint merging is possible only if each keypoint on one side of the face to be joined is matched by a coincident keypoint on the other side. This is commonly the case after a symmetry reflection ( [[arsym|ARSYM]] or [[vsymm|VSYMM]] ) or a copy ( [[agen|AGEN]] or [[vgen|VGEN]] ), especially for a model built entirely in Mechanical APDL rather than imported from a CAD system. When the geometry is extremely precise, and the configuration is correct for keypoint merging, **NUMMRG** is more efficient and robust than [[aglue|AGLUE]] or [[vglue|VGLUE]].

**Model Accuracy**

As with all boolean operations, gluing requires that the input entities meet the current boolean tolerance (BTOL). Otherwise, [[aglue|AGLUE]] or [[vglue|VGLUE]] may fail. In such cases, relaxing the tolerance may allow the glue to complete. An advantage of gluing is that it is unlikely to degrade the accuracy of a geometric model. Keypoint merging can operate on almost any combination of entities (although you may have to override the default tolerances on **NUMMRG** ). However, it can also introduce or increase accuracy flaws, making later boolean operations less likely to succeed. If the input tolerances are too large, **NUMMRG** can collapse out small lines, areas, or volumes you intended to keep, possibly rendering the model unusable.

**Mesh Status**

As with all boolean operations, gluing requires that the input entities be unmeshed. Keypoint merging is effective for meshed models under the right conditions. More information on keypoint merging follows.

Merging Solid Model Entities:

When merging solid model entities ( `Label` = KP or ALL), keypoint locations are used as the basis for merging. Once keypoints are merged, any higher order solid model entities (lines, areas, and volumes), regardless of their select status or attachment to the merged keypoints, are considered for merging.

Keypoints that are attached to lines will be merged only if:

- ΔX, ΔY, and ΔZ are each less than `TOLER`

where,

- ΔX is the X component of the distance between keypoints, \* ΔY is the Y component of the distance between keypoints, and \* ΔZ is the Z component of the distance between keypoints;

and

- (equation omitted) is less than 1E-5 times the length of the longest line attached to those keypoints (internal relative solid model tolerance), or (equation omitted) is less than `GTOLER` (global solid model tolerance) if specified.

The `TOLER` field is a consideration tolerance. If a keypoint is within `TOLER` of another keypoint, then those two keypoints are candidates to be merged. If, when "moving" the higher numbered keypoint, the distance exceeds the internal relative solid model tolerance, or the global solid model tolerance ( `GTOLER` ) if specified, the keypoints will not be merged. Lines, areas, and volumes are considered for merging in a similar manner.

The internal relative solid model tolerance should be overridden by the global solid model tolerance ( `GTOLER` ) only when absolutely necessary. `GTOLER` is an absolute tolerance; if specified, relative lengths of lines in the model will no longer be considered in the merge operation. If `GTOLER` is too large, you can "merge-out" portions of your model accidently, effectively defeaturing the model. If using `GTOLER`, it is good practice so first save the database before issuing **NUMMRG** (as undesired merges of solid model entities could occur).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NUMMRG.html
