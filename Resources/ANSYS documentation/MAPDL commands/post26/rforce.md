---
apdl: "RFORCE"
method: rforce
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.rforce
generated: 2026-08-22
tags: [mapdl-command]
---

# RFORCE

PyMAPDL: `mapdl.rforce(nvar='', node='', item='', comp='', name='', **kwargs)`

Specifies the total reaction force data to be stored.

## Parameters

**nvar**: Arbitrary reference number assigned to this variable (2 to NV ( [[numvar|NUMVAR]] )). Overwrites any existing results for this variable.

**node**: Node for which data are to be stored. If `NODE` = P, graphical picking is enabled (valid only in the GUI).

**item**: Label identifying the item. Valid item labels are shown in the table below. Some items also require a component label.

**comp**: Component of the item (if required). Valid component labels are shown in the table below.

**name**: Thirty-two character name identifying the item on printouts and displays. Defaults to an eight character label formed by concatenating the first four characters of the `Item` and `Comp` labels.

## Notes

Defines the total reaction force data (static, damping, and inertial components) to be stored from single pass ( [[antype|ANTYPE]],STATIC or TRANS) solutions or from the expansion pass of mode- superposition ( [[antype|ANTYPE]],HARMIC or TRANS) solutions.

### RFORCE - Valid Item and Component Labels

Valid item and component labels for node results are:

| Item       | Comp  | Description                                   |
|------------|-------|-----------------------------------------------|
| F          | X,Y,Z | X, Y, or Z structural force                   |
| M          | X,Y,Z | X, Y, or Z structural moment                  |
| HEAT\[ \]  |       | Heat flow                                     |
| FLOW       |       | Fluid flow                                    |
| AMPS       |       | Current flow                                  |
| FLUX       |       | Magnetic flux                                 |
| CSG        | X,Y,Z | X, Y, or Z magnetic current segment component |
| RATE       |       | Diffusion flow rate                           |
| VLTG       |       | Voltage drop                                  |
| CURT       |       | Current                                       |
| CHRG       |       | Charge                                        |

For `SHELL131` and `SHELL132` elements with KEYOPT(3) = 0 or 1, use the labels HBOT, HE2, HE3,. .., HTOP instead of HEAT.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RFORCE.html
