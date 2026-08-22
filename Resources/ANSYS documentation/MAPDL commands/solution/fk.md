---
apdl: "FK"
method: fk
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_forces.SolidForces.fk
generated: 2026-08-22
tags: [mapdl-command]
---

# FK

PyMAPDL: `mapdl.fk(kpoi='', lab='', value='', value2='', **kwargs)`

Defines force loads at keypoints.

## Parameters

**kpoi**: Keypoint at which force is to be specified. If ALL, apply to all selected keypoints ( [[ksel|KSEL]] ). If `KPOI` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `KPOI`.

**lab**

Valid force labels are:

- **Structural labels** : FX, FY, or FZ (forces); MX, MY, or MZ (moments).
- **Thermal labels** : HEAT, HBOT, HE2, HE3,..., HTOP (heat flow).
- **Fluid label** : FLOW (fluid flow).
- **Electric labels** : AMPS (current flow), CHRG (electric charge).
- **Magnetic labels** : FLUX (magnetic flux); CSGZ (magnetic current segment).
- **Diffusion label** : RATE (diffusion flow rate).

**value**: Force value or table name reference for specifying tabular boundary conditions. To specify a table, enclose the table name in percent signs (%), for example, **FK**, `KPOI`, HEAT,`tabname`). Use the [[dim|*DIM]] command to define a table.

**value2**: Second force value (if any). If the analysis type and the force allow a complex input, `VALUE` (above) is the real component and `VALUE2` is the imaginary component.

## Notes

Forces may be transferred from keypoints to nodes with the [[ftran|FTRAN]] or [[sbctran|SBCTRAN]] commands. See the [[f|F]] command for a description of force loads.

Tabular boundary conditions ( `VALUE` = `tabname`) are available only for the following labels: Fluid (FLOW), Electric (AMPS), Structural force (FX, FY, FZ, MX, MY, MZ), and Thermal (HEAT, HBOT, HE2, HE3,..., HTOP).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FK.html
