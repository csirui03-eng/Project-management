---
apdl: "CYCLIC"
method: cyclic
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.cyclic
generated: 2026-08-22
tags: [mapdl-command]
---

# CYCLIC

PyMAPDL: `mapdl.cyclic(nsector='', angle='', kcn='', name='', usrcomp='', usrnmap='', **kwargs)`

Specifies a cyclic symmetry analysis.

**Command default:**

The default **CYCLIC** command (issuing the command with no arguments) detects the number of sectors ( `NSECTOR` ), the sector angle ( `ANGLE` ), and the coordinate system ( `KCN` ) based upon the existing solid or finite-element model. The command also detects sector low- and high-edge components in most cases and assigns the default root name CYCLIC to the components.

## Parameters

**nsector**

The number of sectors in the full 360 degrees, or one of the following options:

- `STATUS` - Indicates the current cyclic status.

- `OFF` - Resets model to normal (non-cyclic) status and removes the duplicate sector if it exists. This option also deletes automatically detected edge components (generated when `USRCOMP` = 0).

- `UNDOUBLE` - Removes the duplicate sector if it exists. The duplicate sector is created during the solution ( [[solve|SOLVE]] ) stage of a modal cyclic symmetry analysis.

  The duplicate sector is necessary for displaying cyclic symmetry analysis results during postprocessing ( [[post1|/POST1]] ).

If you specify a value of STATUS, OFF or UNDOUBLE, the command ignores all remaining arguments.

**angle**: The sector angle in degrees.

**kcn**: An arbitrary reference number assigned to the cyclic coordinate system. The default value of 0 specifies automatic detection.

**name**

The root name of sector low- and high-edge components (line, area, or node components). The default root name (when `USRCOMP` = 0) is CYCLIC. A root name that you specify can contain up to 11 characters.

The naming convention for each low- and high-edge component pair is either of the following:

- `Name` m `xx` l, `Name` m `xx` h (potentially matched node patterns)
- `Name` u `xx` l, `Name` u `xx` h (potentially unmatched node patterns)

The `Name` value is the default ( CYCLIC ) or specified root name and `xx` is the component pair ID number (sequential, starting at 01).

**usrcomp**: The number of pairs of user-defined low- and high-edge components on the cyclic sector (if any). The default value of 0 specifies automatic detection of sector edges; however, the automatic setting is not valid in all cases. (For more information, see the Notes section below.) If the value is greater than 0, no verification of user-defined components occurs.

**usrnmap**

The name of a user-defined array specifying the matching node pairs between the sector low and high edges. Valid only when `USRCOMP` = 0. Skips the automatic detection of sector edges. Node pairs may be input in any order, but the low edge node must be the first entry in each pair.

``` apdl
*DIM,MYMAP,ARRAY,2,14    ! specifying 14 low-high edge node pairs
*set,mymap(1, 1), 107, 108       ! low node 107 <> high node 108
*set,mymap(1, 2), 147, 211       ! low node 147 <> high node 211
*set,mymap(1, 3), 110, 109       ! low node 110 <> high node 109
        ! etc for node pairs 4 through 14
cyclic,12,,1,,,MYMAP             ! use array MYMAP to generate cyclic CEs
```

## Notes

You can input your own value for `NSECTOR`, `ANGLE` or `KCN` ; if you do so, the command verifies argument values before executing.

When `USRCOMP` = 0 and `UsrNMap` = blank (default), the **CYCLIC** command automatically detects [low- and high-edge components](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycedgecomp.html#) for models that consist of any combination of line, area, or volume elements. If a solid model exists, however, the command uses only the lines, areas, and/or volumes to determine the low- and high-edge components; the elements, if any, are ignored.

Nodes will be automatically rotated unless [[cycopt|CYCOPT]],USRROT,YES has been specified.

If you issue a [[cycopt|CYCOPT]],TOLER command to set a tolerance for edge-component pairing before issuing the **CYCLIC** command, the **CYCLIC** command uses the specified tolerance when performing automatic edge-component detection.

For 2D models, autodetection does not consider the [[csys|CSYS]],5 or [[csys|CSYS]],6 coordinate system specification. Autodetection for 180 degree (two-sector) models is not possible unless a central hole exists.

The **CYCLIC** command sets values and keys so that, if possible, the area-mesh ( [[amesh|AMESH]] ) or volume-mesh ( [[vmesh|VMESH]] ) command meshes the sector with matching node and element face patterns on the low and high edges. (The command has no effect on any other element-creation command.)

Issue the **CYCLIC** command prior to the meshing command to, if possible, produce a mesh with identical node and element patterns on the low and high sector edges. Only the [[amesh|AMESH]] or [[vmesh|VMESH]] commands can perform automated matching. (Other meshing operation commands such as [[vsweep|VSWEEP]] cannot.) If you employ a meshing operation other than [[amesh|AMESH]] or [[vmesh|VMESH]], you should ensure that node and element face patterns match, if desired. The **CYCLIC** command output indicates whether each edge-component pair has or can produce a matching node pair.

A cyclic solution (via the [[solve|SOLVE]] command) allows dissimilar mesh patterns on the extreme boundaries of a cyclically symmetric model. The allowance for dissimilar patterns is useful when you have only finite-element meshes for your model but not the geometry data necessary to remesh it to obtain identical node patterns. In such cases, it is possible to obtain solution results, although perhaps at the expense of accuracy. A warning message appears because results may be degraded near the sector edges.

The constraint equations (CEs) that tie together the low and high edges of your model are generated at the solution stage of the analysis from the low- and high-edge components (and nowhere else). You should verify that automatically detected components are in the correct locations and that you can account for all components; to do so, you can list ( [[cmlist|CMLIST]] ) or plot ( [[cmplot|CMPLOT]] ) the components.

If you issue the **CYCLIC** command after meshing and have defined element types with rotational degrees of freedom (DOFs), Mechanical APDL generates cyclic CEs for rotational DOFs that may not exist on the sector boundaries. Issue [[cycopt|CYCOPT]],DOF to prevent unused rotational terms from being generated.

Modal cyclic symmetry analysis is supported by the following eigensolvers:

- Block Lanczos ( [[modopt|MODOPT]],LANB)
- PCG Lanczos ( [[modopt|MODOPT]],LANPCG)
- Super Node ( [[modopt|MODOPT]],SNODE)
- Subspace ( [[modopt|MODOPT]],SUBSP)

To learn more about analyzing a cyclically symmetric structure, see the [Cyclic Symmetry Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/cycsym_example.html).

When using the **CYCLIC** command to automatically detect the sector, if an area is defined with the [[al|AL]] command, the lines need to be oriented to form the closed curve.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYCLIC.html
