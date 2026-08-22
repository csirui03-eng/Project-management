---
apdl: "EINTF"
method: eintf
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.eintf
generated: 2026-08-22
tags: [mapdl-command]
---

# EINTF

PyMAPDL: `mapdl.eintf(toler='', k='', tlab='', kcn='', dx='', dy='', dz='', knonrot='', **kwargs)`

Defines two-node elements between coincident or offset nodes.

## Parameters

**toler**: Tolerance for coincidence (based on maximum Cartesian coordinate difference for node locations and on angle differences for node orientations). Defaults to 0.0001. Only nodes within the tolerance are considered to be coincident.

**k**: Only used when the type of the elements to be generated is `PRETS179`. `K` is the pretension node that is common to the pretension section that is being created. If `K` is not specified, it is created automatically and will have an Mechanical APDL-assigned node number. If `K` is specified but does not already exist, it will be created automatically but will have the user- specified node number. `K` cannot be connected to any existing element.

**tlab**

Nodal number ordering. Allowable values are:

- `LOW` - The 2-node elements are generated from the lowest numbered node to the highest numbered node.
- `HIGH` - The 2-node elements are generated from the highest numbered node to the lowest numbered node.
- `REVE` - Reverses the orientation of the selected 2-node element.

**kcn**: In coordinate system `KCN`, elements are created between node 1 and node 2 (= node 1 + dx dy dz).

**dx**, **dy**, **dz**: Node location increments that define the node offset in the active coordinate system (DR, Dθ, DZ for cylindrical and DR, Dθ, DΦ for spherical or toroidal).

**knonrot**: When `KNONROT` = 0, the nodes coordinate system is not rotated. When `KNONROT` = 1, the nodes belonging to the elements created are rotated into coordinate system `KCN` (see [[nrotat|NROTAT]] command description).

## Notes

Defines 2-node elements (such as gap elements) between coincident or offset nodes (within a tolerance). May be used, for example, to "hook" together elements interfacing at a seam, where the seam consists of a series of node pairs. One element is generated for each set of two coincident nodes. For more than two coincident or offset nodes in a cluster, an element is generated from the lowest numbered node to each of the other nodes in the cluster. If fewer than all nodes are to be checked for coincidence, use the [[nsel|NSEL]] command to select the nodes. Element numbers are incremented by one from the highest previous element number. The element type must be set ( [[et|ET]] ) to a 2-node element before issuing this command. Use the [[cpintf|CPINTF]] command to connect nodes by coupling instead of by elements. Use the [[ceintf|CEINTF]] command to connect the nodes by constraint equations instead of by elements.

For contact element `CONTA178`, the tolerance is based on the maximum Cartesian coordinate difference for node locations only. The angle differences for node orientations are not checked.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EINTF.html
