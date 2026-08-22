---
apdl: "FDELE"
method: fdele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_forces.FeForces.fdele
generated: 2026-08-22
tags: [mapdl-command]
---

# FDELE

PyMAPDL: `mapdl.fdele(node='', lab='', nend='', ninc='', lkey='', **kwargs)`

Deletes force loads on nodes.

## Parameters

**node**: Node for which force is to be deleted. If ALL, `NEND` and `NINC` are ignored and forces are deleted on all selected nodes ( [[nsel|NSEL]] ). If `NODE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE`.

**lab**

If ALL, use all appropriate labels. Valid force labels are:

- **Structural labels** : FX, FY, or FZ (forces); MX, MY, or MZ (moments).
- **Thermal labels** : HEAT, HBOT, HE2, HE3,..., HTOP (heat flow).
- **Fluid label** : FLOW (fluid flow).
- **Electric labels** : AMPS (current flow), CHRG (electric charge).
- **Magnetic labels** : FLUX (magnetic flux); CSGZ (magnetic current segment).
- **Diffusion label** : RATE (diffusion flow rate).

**nend**, **ninc**: Delete forces from `NODE` to `NEND` (defaults to `NODE` ) in steps of `NINC` (defaults to 1).

**lkey**

Lock key:

- `(blank)` - The DOF is not locked (default).
- `FIXED` - Displacement on the specified degrees of freedom ( `Lab` ) is locked. The program prescribes the degree of freedom to the “current” relative displacement value in addition to deleting the force. If a displacement constraint (for example, [[d|D]] command) is applied in conjunction with this option, the actual applied displacement will be ramped during the next load step. The displacement is ramped from the current value to the newly defined value. This option is only valid for the following labels: FX, FY, FZ, MX, MY, MZ. This option is intended primarily for use in the Ansys Workbench interface to apply an increment length adjustment (bolt pretension loading).

## Notes

The node and the degree of freedom label corresponding to the force must be selected ( [[nsel|NSEL]], [[dofsel|DOFSEL]] ).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FDELE.html
