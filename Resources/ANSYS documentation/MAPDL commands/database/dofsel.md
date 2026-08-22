---
apdl: "DOFSEL"
method: dofsel
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.dofsel
generated: 2026-08-22
tags: [mapdl-command]
---

# DOFSEL

PyMAPDL: `mapdl.dofsel(type_='', dof1='', dof2='', dof3='', dof4='', dof5='', dof6='', **kwargs)`

Selects a DOF label set for reference by other commands.

**Command default:**

Degree of freedom (and the corresponding force) labels are determined from the model.

## Parameters

**type_**

Label identifying the type of select:

- `S` - Select a new set of labels.
- `A` - Add labels to the current set.
- `U` - Unselect (remove) labels from the current set.
- `ALL` - Restore the full set of labels.
- `STAT` - Display the current select status.

**dof1**, **dof2**, **dof3**, **dof4**, **dof5**, **dof6**

Used only with `Type` = S, A, or U. Valid lables are:

- **Structural labels** : UX, UY, or UZ (displacements); U (UX, UY, and UZ) ; ROTX, ROTY, or ROTZ (rotations); ROT (ROTX, ROTY, and ROTZ); DISP (U and ROT); HDSP (Hydrostatic pressure).
- **Thermal labels** : TEMP, TBOT, TE2, TE3,..., TTOP (temperature).
- **Acoustic labels** : PRES (pressure); UX, UY, or UZ (displacements for FSI coupled elements).
- **Electric labels** : VOLT (voltage); EMF (electromotive force drop); CURR (current).
- **Magnetic labels** : MAG (scalar magnetic potential); AZ (vector magnetic potential); A (AZ); CURR (current).
- **Structural force labels** : FX, FY, or FZ (forces); F (FX, FY, and FZ); MX, MY, or MZ (moments); M (MX, MY, and MZ); FORC (F and M); DVOL (fluid mass flow rate).
- **Thermal force labels** : HEAT, HBOT, HE2, HE3,..., HTOP (heat flow).
- **Fluid flow force label** : FLOW (fluid flow).
- **Electric force labels** : AMPS (current flow); CHRG (electric charge).
- **Magnetic force labels** : FLUX (scalar magnetic flux); CSGZ (magnetic current segment).
- **Diffusion labels** : CONC (concentration); RATE (diffusion flow rate).

## Notes

Selects a degree of freedom label set for reference by other commands. The label set is used on certain commands where ALL is either input in the degree of freedom label field or implied. The active label set has no effect on the solution degrees of freedom. Specified labels which are not active in the model (from the [[et|ET]] or [[dof|DOF]] command) are ignored. As a convenience, a set of force labels corresponding to the degree of freedom labels is also selected. For example, selecting UX also causes FX to be selected (and vice versa). The force label set is used on certain commands where ALL is input in the force label field.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DOFSEL.html
