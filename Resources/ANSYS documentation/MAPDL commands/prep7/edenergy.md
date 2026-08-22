---
apdl: "EDENERGY"
method: edenergy
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edenergy
generated: 2026-08-22
tags: [mapdl-command]
---

# EDENERGY

PyMAPDL: `mapdl.edenergy(hgen='', swen='', sien='', rlen='', **kwargs)`

Specifies energy dissipation controls for an explicit dynamics

analysis.

## Parameters

**hgen**

Hourglass energy control key:

OFF or 0 - Hourglass energy is not computed.

ON or 1 - Hourglass energy is computed and included in the energy balance (default).

**swen**

Stonewall energy dissipation control key:

OFF or 0 - Stonewall energy dissipation is not computed.

ON or 1 - Stonewall energy dissipation is computed and included in the energy balance  
(default).

**sien**

Sliding interface energy dissipation control key:

OFF or 0 - Sliding interface energy dissipation is not computed.

ON or 1 - Sliding interface energy dissipation is computed and included in the energy  
balance (default).

**rlen**

Rayleigh (damping) energy dissipation control key:

OFF or 0 - Rayleigh energy dissipation is not computed.

ON or 1 - Rayleigh energy dissipation is computed and included in the energy balance  
(default).

## Notes

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
