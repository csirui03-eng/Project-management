---
apdl: "MAP2DTO3D"
method: map2dto3d
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_2d_to_3d.Analysis2DTo3D.map2dto3d
generated: 2026-08-22
tags: [mapdl-command]
---

# MAP2DTO3D

PyMAPDL: `mapdl.map2dto3d(action='', value1='', value2='', **kwargs)`

Initiates a 2D to 3D analysis and maps variables.

## Parameters

**action**

The 2D to 3D analysis action to perform:

- `START` - Start the analysis process by rebuilding the 2D analysis database ( `.db` ) based on the specified load step and substep information, and update nodes to their deformed positions in the 2D mesh.
  - `VALUE1` - The load step number at which 2D to 3D analysis should occur. The default value is the highest load step number found in the `Jobname.Rnnn` files (for the current jobname and in the current directory).
  - `VALUE2` - The substep number of the specified load step ( `VALUE1` ) at which the 2D to 3D analysis should occur. The default value is the highest substep number found in the specified load step in the `Jobname.Rnnn` files (for the current jobname and in the current directory).
- `FINISH` - Maps boundary conditions and loads from the 2D mesh to the extruded 3D mesh. ( VALUE1 and VALUE2 are not used.)
- `SOLVE` - Map nodal and element solutions from 2D to 3D and rebalance the results.
  - `VALUE1` - The maximum number of substeps allowed during rebalancing. Default = 500.

**value1**, **value2**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MAP2DTO3D.html) for further information.

## Notes

The **MAP2DTO3D** command initiates the 2D to 3D analysis process, sets analysis options, rebuilds the database, and maps the solution variables from the 2D mesh to the 3D mesh.

Before issuing this command, clear the database ( [[clear|/CLEAR]] ).

For more information, see [2D to 3D Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_ADV2DTO3DREST.html)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MAP2DTO3D.html
