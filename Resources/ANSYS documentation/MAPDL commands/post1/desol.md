---
apdl: "DESOL"
method: desol
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.set_up.SetUp.desol
generated: 2026-08-22
tags: [mapdl-command]
---

# DESOL

PyMAPDL: `mapdl.desol(elem='', node='', item='', comp='', v1='', v2='', v3='', v4='', v5='', v6='', **kwargs)`

Defines or modifies solution results at a node of an element.

## Parameters

**elem**: Element number for which results are defined or modified. If ALL, apply to all selected elements ( [[esel|ESEL]] ).

**node**: Node of element (actual node number, not the position) to which results are specified. If ALL, specify results for all selected nodes ( [[nsel|NSEL]] ) of element. If `NODE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE`.

**item**: Label identifying results. Valid item labels are shown in *DESOL - Valid Item and Component Labels* below. Some items also require a component label ( `Comp` ).

**comp**: Component of the item (if required); see *DESOL - Valid Item and Component Labels*.

**v1**, **v2**, **v3**, **v4**, **v5**, **v6**: Additional values (if any) assigned to the remaining components (in the order corresponding to the `Comp` list shown below) for the specified `Item` (starting from the specified `Comp` label and proceeding to the right).

## Notes

The **DESOL** command defines or modifies solution results in the database at a node of an area or volume element. For example, **DESOL**,35,50,S,X,1000,2000,1000 assigns values 1000, 2000, and 1000 to SX, SY, and SZ (respectively) of node 50 of element 35.

The settings of the POST1 [[force|FORCE]], [[shell|SHELL]], and [[layer|LAYER]] commands, if applicable, further specify which database items are affected.

For layered composite shells, specify the current element layer ( [[layer|LAYER]] ) before issuing the **DESOL** command.

All data is stored in the solution coordinate system but is displayed in the results coordinate system ( [[rsys|RSYS]] ). To list the current results, use the [[presol|PRESOL]] command.

Modified solution results are not saved automatically. To save separate records of modified results, use either the [[rappnd|RAPPND]] or [[lcwrite|LCWRITE]] command.

Result items are available depending on element type; check the individual element for availability. Valid item and component labels for element results are:

### DESOL - Valid Item and Component Labels

| Item | Comp                | Description                                    |
|------|---------------------|------------------------------------------------|
| ELEM |                     | Element number.                                |
| S    | X, Y, Z, XY, YZ, XZ | Component stress.                              |
| EPEL | X, Y, Z, XY, YZ, XZ | Component elastic strain.                      |
| EPTH | X, Y, Z, XY, YZ, XZ | Component thermal strain.                      |
| EPPL | X, Y, Z, XY, YZ, XZ | Component plastic strain.                      |
| EPCR | X, Y, Z, XY, YZ, XZ | Component creep strain.                        |
| EPSW |                     | Swelling strain.                               |
| NL   | SEPL                | Equivalent stress (from stress-strain curve).  |
| "    | SRAT                | Stress state ratio.                            |
| "    | HPRES               | Hydrostatic pressure.                          |
| "    | EPEQ                | Accumulated equivalent plastic strain.         |
| "    | PSV                 | Plastic state variable.                        |
| "    | PLWK                | Plastic work/volume.                           |
| SEND | ELASTIC             | Elastic strain energy density.                 |
| "    | PLASTIC             | Plastic strain energy density.                 |
| "    | CREEP               | Creep strain energy density.                   |
| TG   | X, Y, Z             | Component thermal gradient.                    |
| TF   | X, Y, Z             | Component thermal flux.                        |
| PG   | X, Y, Z             | Component pressure gradient.                   |
| EF   | X, Y, Z             | Component electric field.                      |
| D    | X, Y, Z             | Component electric flux density.               |
| H    | X, Y, Z             | Component magnetic field intensity.            |
| B    | X, Y, Z             | Component magnetic flux density.               |
| CG   | X, Y, Z             | Concentration gradient                         |
| DF   | X, Y, Z             | Diffusion flux density                         |
| FMAG | X, Y, Z             | Component electromagnetic force.               |
| F    | X, Y, Z             | X, Y, or Z structural force.                   |
| M    | X, Y, Z             | X, Y, or Z structural moment.                  |
| HEAT |                     | Heat flow.                                     |
| FLOW |                     | Fluid flow.                                    |
| AMPS |                     | Current flow.                                  |
| FLUX |                     | Magnetic flux.                                 |
| CSG  | X, Y, Z             | X, Y, or Z magnetic current segment component. |
| RATE |                     | Diffusion flow rate                            |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DESOL.html
