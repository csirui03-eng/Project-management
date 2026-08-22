---
apdl: "PRVECT"
method: prvect
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.prvect
generated: 2026-08-22
tags: [mapdl-command]
---

# PRVECT

PyMAPDL: `mapdl.prvect(item='', lab2='', lab3='', labp='', **kwargs)`

Prints results as vector magnitude and direction cosines.

## Parameters

**item**: Predefined vector item (from *PRVECT - Valid Item and Component Labels* below) or a label identifying the i-component of a user-defined vector.

**lab2**: Label identifying the j-component of a user-defined vector. In most cases, this value must be blank if `Item` is selected from *PRVECT - Valid Item and Component Labels*. Individual principal stresses ( `Item` = S) or principal strains ( `Item` = EP `xx` ) may be printed by specifying the value as 1, 2, or 3.

**lab3**: Label identifying the k-component of a user-defined vector. Must be blank if `Item` is selected from list below or for 2D user defined vector.

**labp**: Label assigned to resultant vector for printout labeling (defaults to `Item` ).

## Notes

Prints various solution results as vector magnitude and direction cosines for the selected nodes and/or elements. For example, **PRVECT**,U prints the displacement magnitude and its direction cosines for all selected nodes. For nodal degree of freedom vector results, direction cosines are with respect to the results coordinate system RSYS. For element results, direction cosines are with respect to the global Cartesian system. Item components may be printed with the [[prnsol|PRNSOL]] command. Various results also depend upon the recalculation method and the selected results location ( [[layer|LAYER]], [[shell|SHELL]], [[nsel|NSEL]], and [[esel|ESEL]] ). Items may be selected from a set of recognized vector labels ( `Item` ) or a vector may be defined from up to three scalar labels ( `Item`, `Lab2`, `Lab3` ). Scalar labels may be user-defined with the [[etable|ETABLE]] command.

Portions of this command are not supported by PowerGraphics ( [[graphics|/GRAPHICS]],POWER).

### PRVECT - Valid Item and Component Labels

| Item | Comp | Description |
|----|----|----|
| Valid item labels for nodal degree of freedom vector results are: |  |  |
| U |  | Structural displacement vector magnitude and direction cosines. |
| ROT |  | Structural rotation vector magnitude and direction cosines. |
| V |  | Velocity vector magnitude and direction cosines. |
| A |  | Magnetic vector potential vector magnitude and direction cosines. |
| Valid item labels for element results are: |  |  |
| S |  | Principal stresses and direction cosines. |
| EPTO |  | Principal total strains (EPEL + EPPL + EPCR) and direction cosines. |
| EPEL |  | Principal elastic strains and direction cosines. |
| EPPL |  | Principal plastic strains and direction cosines. |
| EPCR |  | Principal creep strains and direction cosines. |
| EPTH |  | Principal thermal strains and direction cosines. |
| EPDI |  | Principal diffusion strains and direction cosines. |
| TG |  | Thermal gradient vector sum and direction cosines. |
| TF |  | Thermal flux vector sum and direction cosines. |
| PG |  | Velocity or energy density flux (room acoustics) vector sum and direction cosines. |
| EF |  | Electric field vector sum and direction cosines. |
| D |  | Electric flux density vector sum and direction cosines. |
| H |  | Magnetic field intensity vector sum and direction cosines. If `Lab2` is blank, Item is interpreted as one of the predefined labels; otherwise, Item is interpreted as a user-defined [[et\|ET]] label and the program requests a non-blank `Lab2` / `Lab3` according to the dimension of the problem. |
| B |  | Magnetic flux density vector sum and direction cosines. |
| CG |  | Concentration gradient vector sum and direction cosines. |
| DF |  | Diffusion flux density vector sum and direction cosines. |
| FMAG |  | Electromagnetic force vector sum and direction cosines. |
| P |  | Poynting vector sum and direction cosines. |
| JS |  | Source current density vector sum and direction cosines for low-frequency magnetic analyses. Total current density vector sum and direction cosines (sum of conduction and displacement current densities) in low frequency electric analyses. |
| JT |  | Total measurable current density vector sum and direction cosines in low-frequency electromagnetic analyses. (Conduction current density vector sum and direction cosines in a low-frequency electric analysis.) |
| JC |  | Conduction current density vector sum and direction cosines for elements that support conduction current calculation. |
| SNDI |  | Sound intensity vector sum and direction cosines. |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRVECT.html
