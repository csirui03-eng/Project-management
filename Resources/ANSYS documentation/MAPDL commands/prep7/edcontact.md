---
apdl: "EDCONTACT"
method: edcontact
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edcontact
generated: 2026-08-22
tags: [mapdl-command]
---

# EDCONTACT

PyMAPDL: `mapdl.edcontact(sfsi='', rwpn='', ipck='', shtk='', peno='', stcc='', orie='', cspc='', penchk='', **kwargs)`

Specifies contact surface controls for an explicit dynamics analysis.

## Parameters

**sfsi**: Scale factor for sliding interface penalties. Defaults to 0.1.

**rwpn**: Scale factor for rigid wall penalties (defaults to 0). If RWPN = 0, rigid bodies interacting with rigid walls are not considered. If RWPN\>0, rigid bodies interact with fixed rigid walls. A value of 1.0 should be optimal; however, this may be problem dependent.

**ipck**

Initial contact surface penetration checking option:

1 - No checking.

2 - Full check of initial penetration is performed (default).

**shtk**

Shell thickness contact option for surface-to-surface and nodes-to- surface contact (see Notes below):

0 - Thickness is not considered (default).

1 - Thickness is considered, except in rigid bodies.

2 - Thickness is considered, including rigid bodies.

**peno**

Penalty stiffness option (options 4 and 5 are useful for metal forming calculations):

1 - Minimum of master segment and slave node (default).

2 - Use master segment stiffness.

3 - Use slave node value.

4 - Use area or mass weighted slave node value.

5 - Use slave node value inversely proportional to shell thickness. (This may  
require special scaling and is not generally recommended.)

**stcc**

Shell thickness change option for single surface contact:

1 - Shell thickness changes are not considered (default).

2 - Shell thickness changes are included.

**orie**

Option for automatic reorientation of contact surface segments during initialization:

1 - Activate for automated (part ID) input only (default).

2 - Activate for manual (nodal component) and automated (part ID) input.

3 - Do not activate.

**cspc**: Contact surface penetration check multiplier, used if small penetration checking is on (PENCHK = 1 or 2). Defaults to 4.

**penchk**

Small penetration check, used only for contact types STS, NTS, OSTS, TNTS, and TSTS. If the contact surface node penetrates more than the target thickness times CSPC, the penetration is ignored and the contacting node is set free. The target thickness is the element thickness for shell elements, or 1/20 of the shortest diagonal for solid elements.

0 - Penetration checking is off (default).

1 - Penetration checking is on.

2 - Penetration checking is on, but shortest diagonal is used.

## Notes

The thickness offsets are always included in single surface, automatic surface-to-surface, and automatic nodes-to-surface contact. The shell thickness change option must be used \[EDSHELL,,,1\] and a nonzero value must be specified for SHTK before the shell thickness changes can be included in the surface-to-surface contact type. Additionally, STCC must be set to 2 if thickness changes are to be included in the single surface contact algorithms.

To reset the contact options to default values, issue the EDCONTACT command with no fields specified.

This command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
