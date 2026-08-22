---
apdl: "PRRSOL"
method: prrsol
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.prrsol
generated: 2026-08-22
tags: [mapdl-command]
---

# PRRSOL

PyMAPDL: `mapdl.prrsol(lab='', **kwargs)`

Prints the constrained node reaction solution.

## Parameters

**lab**

Nodal reaction load type. If blank, use the first ten of all available labels. Valid labels are:

- **Structural force labels** : FX, FY or FZ (forces); F (FX, FY and FZ); MX, MY or MZ (moments); M (MX, MY and MZ); BMOM (bimoments).
- **Thermal force labels** : HEAT, HBOT, HE2, HE3,..., HTOP (heat flow).
- **Fluid force labels** : FLOW (fluid flow); VFX, VFY and VFZ (fluid forces); VF (VFX, VFY and VFZ).
- **Electric force labels** : AMPS (current flow); CHRG (charge); CURT (current); VLTG (voltage drop).
- **Magnetic force labels** : FLUX (magnetic flux); CSGZ (magnetic current segment); CURT (current), VLTG (voltage drop).
- **Diffusion labels** : RATE (diffusion flow rate).

## Notes

Prints the constrained node reaction solution for the selected nodes in the sorted sequence. For coupled nodes and nodes in constraint equations, the sum of all reactions in the coupled or constraint equation set appears at the primary node of the set. Results are in the global Cartesian coordinate directions unless transformed ( [[rsys|RSYS]] ).

**PRRSOL** is not valid if any load is applied to a constrained node in the direction of the constraint and any of the following is true:

- [[lcoper|LCOPER]] has been used.
- [[lcase|LCASE]] has been used to read from a load case file.
- The applied loads and constraints in the database are not the ones used to create the results data being processed.

**PRRSOL** provides the total reaction solution (static, plus damping, plus inertial, as appropriate based on the analysis type); however, modal reactions include only the static contribution.

Use [[prrfor|PRRFOR]] instead of **PRRSOL** with the [[force|FORCE]] command to obtain only the static, damping, or inertial components.

When using distributed-memory parallel processing, in a spectrum analysis or a PSD analysis performed with `Elcalc` = YES on the [[spopt|SPOPT]] command, use [[prrfor|PRRFOR]] instead of **PRRSOL** to print the maximum reaction forces (spectrum analysis) or reaction forces variances of 1-σ solutions, as **PRRSOL** may lead to more conservative results.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRRSOL.html
