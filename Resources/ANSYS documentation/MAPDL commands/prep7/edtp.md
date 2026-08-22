---
apdl: "EDTP"
method: edtp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edtp
generated: 2026-08-22
tags: [mapdl-command]
---

# EDTP

PyMAPDL: `mapdl.edtp(option='', value1='', value2='', **kwargs)`

Plots explicit elements based on their time step size.

## Parameters

**option**

Plotting option (default = 1).

1 - Plots the elements with the smallest time step  
sizes. The number of elements plotted and listed is equal to VALUE1 (which defaults to 100). Each element is shaded red or yellow based on its time step value (see "Notes" for details).

2 - Produces the same plot as for OPTION = 1, and also  
produces a list of the plotted elements and their corresponding time step values.

3 - Produces a plot similar to OPTION = 1, except that all  
selected elements are plotted. Elements beyond the first VALUE1 elements are blue and translucent. The amount of translucency is specified by VALUE2. This option also produces a list of the first VALUE1 elements with their corresponding time step values.

**value1**: Number of elements to be plotted and listed (default = 100). For example, if VALUE1 = 10, only the elements with the 10 smallest time step sizes are plotted and listed.

**value2**: Translucency level ranging from 0 to 1 (default = 0.9). VALUE2 is only used when OPTION = 3, and only for the elements plotted in blue. To plot these elements as non-translucent, set VALUE2 = 0.

## Notes

EDTP invokes an ANSYS macro that plots and lists explicit elements based on their time step size. For OPTION = 1 or 2, the number of elements plotted is equal to VALUE1 (default = 100). For OPTION = 3, all selected elements are plotted.

The elements are shaded red, yellow, or blue based on their time step size. Red represents the smallest time step sizes, yellow represents the intermediate time step sizes, and blue represents the largest time step sizes. For example, if you specify VALUE1 = 30, and if T1 is the smallest critical time step of all elements and T30 is the time step of the 30th smallest element, then the elements are shaded as follows:

Translucent blue elements only appear when OPTION = 3.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
