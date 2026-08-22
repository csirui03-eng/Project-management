---
apdl: "EDHGLS"
method: edhgls
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edhgls
generated: 2026-08-22
tags: [mapdl-command]
---

# EDHGLS

PyMAPDL: `mapdl.edhgls(hgco='', **kwargs)`

Specifies the hourglass coefficient for an explicit dynamics analysis.

## Parameters

**hgco**: Hourglass coefficient value (defaults to 0.1). Values greater than 0.15 may cause instabilities.

## Notes

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
