---
apdl: "EDPC"
method: edpc
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edpc
generated: 2026-08-22
tags: [mapdl-command]
---

# EDPC

PyMAPDL: `mapdl.edpc(min_='', max_='', inc='', **kwargs)`

Selects and plots explicit dynamic contact entities.

## Parameters

**min_**: Minimum contact entity number to be selected and plotted (default = 1).

**max_**: Maximum contact entity number to be selected and plotted (default = MIN).

**inc**: Contact entity number increment (default = 1).

## Notes

EDPC invokes an ANSYS macro which selects and plots explicit dynamic contact entities. The plot will consist of nodes or elements, depending on the method (node components or parts) that was used to define the contact surfaces (see the EDCGEN command). For single surface contact definitions, all external surfaces within the model are plotted.

Note:: : EDPC changes the selected set of nodes and elements. After plotting contact entities, you must reselect all nodes and elements (NSEL and ESEL) required for subsequent operations, such as SOLVE

Use the EDCLIST command to list the contact entity numbers for all defined contact.

This command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
