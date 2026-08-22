---
apdl: "EDINT"
method: edint
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edint
generated: 2026-08-22
tags: [mapdl-command]
---

# EDINT

PyMAPDL: `mapdl.edint(shellip='', beamip='', **kwargs)`

Specifies number of integration points for explicit shell and beam

output.

## Parameters

**shellip**: Number of shell integration points used for output (defaults to 3). For element SHELL163, each integration point is associated with a layer. SHELLIP must be 3. If SHELLIP = 3, results are written for the shell top, middle, and bottom. If SHELLIP \>3, then the results for the first SHELLIP layers are written.

**beamip**: Number of beam integration points used for stress output for BEAM161 (defaults to 4).

## Notes

The number of integration points is defined by the element real constant NIP for both the beam elements (in the cross section) and the shell elements (through the thickness).

For shell elements that have only 1 or 2 integration points (NIP = 1 or 2), use the default of SHELLIP = 3. If NIP = 1, the same results are reported at the top, middle, and bottom layers. If the NIP = 2, the results at the bottom correspond to integration point 1, the results at the top correspond to integration point 2, and the results at the middle are an average of the top and bottom results.

For shell elements with 2 x 2 integration points in the plane, the data from the four points are averaged, and there is a single output value for each layer.

If you set BEAMIP = 0, no stress output is written for BEAM161 elements. In this case, the beams will not appear in any POST1 plots because the program assumes they are failed elements.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
