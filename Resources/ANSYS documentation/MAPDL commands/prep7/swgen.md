---
apdl: "SWGEN"
method: swgen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.swgen
generated: 2026-08-22
tags: [mapdl-command]
---

# SWGEN

PyMAPDL: `mapdl.swgen(ecomp='', swrd='', ncm1='', ncm2='', snd1='', snd2='', shrd='', dirx='', diry='', dirz='', itty='', icty='', **kwargs)`

Creates a new spot weld set.

## Parameters

**ecomp**: Name to identify the new spot weld, used for the element component containing the new contact, target, and beam elements generated for the spot weld set.

**swrd**: Spot weld radius.

**ncm1**: Name of a component containing nodes on the first spot weld surface, or a meshed area number for the surface.

**ncm2**: Name of a component containing nodes on the second spot weld surface, or a meshed area number for the surface.

**snd1**

Node number of the first spot weld node corresponding to the first surface ( `NCM1` ). This node can be on or close to the first surface.

To define multiple spot welds between two surfaces, input the name of a table array parameter containing the node information for each spot weld. The table name must be enclosed in % signs (for example, `tabname`). If `SND1` is defined by tabular input, `SND2` is ignored.

**snd2**: Node number of the second spot weld node corresponding to the second surface ( `NCM2` ). This node can be on or close to the second surface. Mechanical APDL creates the node if not specified.

**shrd**: Search radius. Defaults to 4 times the spot weld radius `SWRD`.

**dirx**, **diry**, **dirz**: Spot weld projection direction in terms of normal X, Y, and Z components.

**itty**: Target element type ID.

**icty**: Contact element type ID.

## Notes

This command creates a new spot weld set. You can add more surfaces to the set using [[swadd|SWADD]] after the initial **SWGEN** command. However, the maximum number of allowable surfaces (including the two surfaces used for the original set) for each spot weld set is 11.

`Ecomp`, `SWRD`, `NCM1`, `NCM2`, and `SND1` must be specified. `SND2`, `SHRD`, `DIRX`, `DIRY`, `DIRZ`, `ITTY`, `ICTY` are optional inputs. If the second spot weld node ( `SND2` ) is specified, that node is used to determine the spot weld projection direction, and `DIRX`, `DIRY` and `DIRZ` are ignored.

If `ITTY` (target element ID) is specified, the following corresponding target element key option must be set: KEYOPT(2) = 1.

If `ICTY` (contact element ID) is specified, the following corresponding contact element key options must be set: KEYOPT(2) = 2, KEYOPT(4) = 1, KEYOPT(12) = 5.

After `SND1` and `SND2` are projected onto surface 1 and surface 2, respectively, two new pilot nodes (which represent the spot weld nodes) are generated at the locations of `SND1` and `SND2` and meshed with `TARGE170` target elements ( [[tshap|TSHAP]],PILO).

By default, the contact pair created at each spot weld surface is an MPC-based [force-distributed constraint](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_surfcon.html#strbeamso1703). To use force-distributed constraints based on the Lagrange multiplier method, you must set KEYOPT(2) = 3 for the contact elements after **SWGEN** is issued.

To automatically define multiple spot welds between two surfaces, use tabular input in the `SND1` field. The table array that you input must be a 2D array parameter. For more information, see [Automatic Generation of Multiple Spot Welds](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/ctecautogenmultisw.html#)

To use the relaxation method to eliminate overconstraint, you must set KEYOPT(11) = 1 for the target elements after **SWGEN** is issued.

Issue [[swlist|SWLIST]] and [[swdel|SWDEL]] to list or delete spot welds, respectively. For more information about defining spot welds, see [Creating a Basic Spot Weld Set with SWGEN](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_spwdset.html#ctecswsrchrad)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SWGEN.html
