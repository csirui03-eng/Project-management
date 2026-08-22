---
apdl: "CP"
method: cp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.coupled_dof.CoupledDof.cp
generated: 2026-08-22
tags: [mapdl-command]
---

# CP

PyMAPDL: `mapdl.cp(nset='', lab='', node1='', node2='', node3='', node4='', node5='', node6='', node7='', node8='', node9='', node10='', node11='', node12='', node13='', node14='', node15='', node16='', node17='', **kwargs)`

Defines (or modifies) a set of coupled degrees of freedom.

## Parameters

**nset**

Set reference number:

- `n` - Arbitrary set number.
- `HIGH` - The highest defined coupled set number will be used (default, unless `Lab` = ALL). This option is useful when adding nodes to an existing set.
- `NEXT` - The highest defined coupled set number plus one will be used (default if `Lab` = ALL). This option automatically numbers coupled sets so that existing sets are not modified.

**lab**

Degree of freedom label for coupled nodes (in the nodal coordinate system). Defaults to label previously defined with `NSET` if set `NSET` already exists. A different label redefines the previous label associated with `NSET`. Valid labels are: Structural labels: UX, UY, or UZ (displacements); ROTX, ROTY, or ROTZ (rotations) (in radians); HDSP (hydrostatic pressure). Thermal labels: TEMP, TBOT, TE2, TE3, ..., TTOP (temperature). Fluid labels: PRES (pressure); VX, VY, or VZ (velocities). Electric labels: VOLT (voltage); EMF (electromotive force drop); CURR (current). Magnetic labels: MAG (scalar magnetic potential); AZ (vector magnetic potential); CURR (current). Diffusion label: CONC (concentration).

When `Lab` = ALL:

- Sets are generated for each active degree of freedom (that is, one set for the UX degree of freedom, another set for UY, etc.), and `NSET` is incremented automatically to prevent overwriting existing sets.
- Existing sets are not modified. `NSET` must be a new set number `n` or NEXT.
- The degree of freedom set is determined according to all element types defined and the [[dof|DOF]] command, if used.
- Hydrostatic pressure (HDSP) is not included.

**node1**, **node2**, **node3**, **node4**, **node5**, **node6**, **node7**, **node8**, **node9**, **node10**, **node11**, **node12**, **node13**, **node14**, **node15**, **node16**, **node17**

List of nodes to be included in set. Duplicate nodes are ignored. If a node number is input as negative, the node is deleted from the coupled set. The first node in the list is the primary (retained) node, and the remaining nodes represent the removed degrees of freedom.

If `NODE1` = ALL, `NODE2` through `NODE17` are ignored and all selected nodes ( [[nsel|NSEL]] ) are included in the set, and the node with the lowest node number becomes the primary node.

If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

A component name can be substituted for `NODE1`. The component consists of the node group to be coupled. The node with the lowest node number becomes the primary node among the node group. To display the generated and coupled node sets, issue the [[cplist|CPLIST]] command.

## Notes

Do not include the same degree of freedom in more than one coupled set. Repeat **CP** command for additional nodes.

Coupling degrees of freedom into a set causes the results calculated for one member of the set to be the same for all members of the set. Coupling can be used to model various joint and hinge effects. A more general form of coupling can be done with constraint equations ( [[ce|CE]] ). For structural analyses, a list of nodes is defined along with the nodal directions in which these nodes are to be coupled. As a result of this coupling, these nodes are forced to take the same displacement in the specified nodal coordinate direction. The amount of the displacement is unknown until the analysis is completed. A set of coupled nodes which are not coincident, or which are not along the line of the coupled displacement direction, may produce an applied moment which will not appear in the reaction forces. The actual degrees of freedom available for a particular node depends upon the degrees of freedom associated with element types ( [[et|ET]] ) at that node. For scalar field analysis, this command is used to couple nodal temperatures, pressures, voltages, etc.

A set of coupled nodes which are not coincident, or which are not along the line of the coupled displacement direction, produce an artificial moment constraint. If the structure rotates, a moment may be produced in the coupled set in the form of a force couple. This moment is in addition to the real reaction forces and may make it appear that moment equilibrium is not satisfied by just the applied forces and the reaction forces.

Additional sets of coupled nodes may be generated from a specified set. Degrees of freedom are coupled within a set but are not coupled between sets. No degree of freedom should appear in more than one coupled set. Such an appearance would indicate that at least two sets were in fact part of a single larger set. The first degree of freedom of the coupled set is the "prime" degree of freedom. All other degrees of freedom in the coupled sets are eliminated from the solution matrices by their relationship to the prime degree of freedom. Forces applied to coupled nodes (in the coupled degree of freedom direction) will be summed and applied to the prime degree of freedom. Output forces are also summed at the prime degree of freedom. Degrees of freedom with specified constraints ( [[d|D]] ) should not be included in a coupled set (unless the degree of freedom is prime).

If master degrees of freedom are defined for coupled nodes, only the prime degree of freedom should be so defined. The use of coupled nodes reduces the set of coupled degrees of freedom to only one degree of freedom.

The removed degrees of freedom defined by the **CP** command cannot be included in any [[ce|CE]] or [[cerig|CERIG]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CP.html
