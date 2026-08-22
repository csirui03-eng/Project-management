---
apdl: "F"
method: f
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_forces.FeForces.f
generated: 2026-08-22
tags: [mapdl-command]
---

# F

PyMAPDL: `mapdl.f(node='', lab='', value='', value2='', nend='', ninc='', meshflag='', **kwargs)`

Defines force loads at nodes.

## Parameters

**node**: Node at which force is to be specified. If ALL, `NEND` and `NINC` are ignored and forces are applied to all selected nodes ( [[nsel|NSEL]] ). If `Node` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `Node`.

**lab**

Valid force labels are:

- **Structural labels** : FX, FY, or FZ (forces); MX, MY, or MZ (moments).
- **Thermal labels** : HEAT, HBOT, HE2, HE3,..., HTOP (heat flow).
- **Fluid label** : FLOW (fluid flow).
- **Electric labels** : AMPS (current flow), CHRG (electric charge).
- **Magnetic labels** : FLUX (magnetic flux); CSGZ (magnetic current segment).
- **Diffusion label** : RATE (diffusion flow rate).
- **Viscous-thermal acoustics labels** : FX, FY, FZ ( [volumetric force density](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_acous/acous_excit_src.html#) ).

For structural analyses, DVOL (fluid mass flow rate) is also a valid label. See [[f#Notes|Notes for more information.]]

**value**: Force value or table name reference for specifying tabular boundary conditions. To specify a table, enclose the table name in percent signs (%), for example, **F**, `Node`,HEAT,`tabname`). To define a table, issue [[dim|*DIM]].

**value2**: Second force value (if any). If the analysis type and the force allow a complex input, `VALUE` (above) is the real component and `VALUE2` is the imaginary component.

**nend**, **ninc**: Specifies the same values of force at the nodes ranging from `Node` to `NEND` (defaults to `Node` ), in steps of `NINC` (defaults to 1).

**meshflag**

Specifies how to apply nodal force on the mesh. Valid in a [nonlinear adaptivity analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVREZ.html) when `Lab` = FX / FY / FZ and `Node` is not a component name. Not valid when `Lab` = ALL.

- 0 - Nodal-force loading occurs on the current mesh (default).
- 1 - Nodal-force loading occurs on the initial mesh for nonlinear adaptivity. ( `NEND` and `NINC` are not valid.)

## Notes

The available force loads per node correspond to the degrees of freedom listed under **Degrees of Freedom** in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). If both a force and a constrained degree of freedom ( [[d|D]] ) are specified at the same node, the constraint takes precedence. Forces are defined in the nodal coordinate system. The positive directions of structural forces and moments are along and about the positive nodal axis directions. The node and the degree-of-freedom label corresponding to the force must be selected ( [[nsel|NSEL]], [[dofsel|DOFSEL]] ).

Fluid flow (FLOW) is positive when flow is out of the nodes, and negative when flow is into the nodes.

For hydrostatic fluid elements ( `HSFLD241` and `HSFLD242` ), DVOL is used to specify fluid mass flow rate (with units of mass/time) at the pressure node. This allows fluid to be added or taken out of the fluid elements sharing the pressure node. A fluid density must also be specified ( [[mp|MP]] or [[tb|TB]] ) to apply a volume change corresponding to the prescribed fluid mass flow rate.

Tabular boundary conditions ( `VALUE` = `tabname`) are available only for the following labels: Fluid (FLOW), Electric (AMPS), Structural force (FX, FY, FZ, MX, MY, MZ), Thermal (HEAT, HBOT, HE2, HE3,..., HTOP), Diffusion (RATE). Tabular boundary conditions are valid only in static ( [[antype|ANTYPE]],STATIC), full transient ( [[antype|ANTYPE]],TRANS), full harmonic ( [[antype|ANTYPE]], HARMIC), modal superposition harmonic and modal superposition transient analyses.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_F.html
