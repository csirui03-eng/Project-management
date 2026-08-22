---
apdl: "EDDBL"
method: eddbl
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.eddbl
generated: 2026-08-22
tags: [mapdl-command]
---

# EDDBL

PyMAPDL: `mapdl.eddbl(key='', **kwargs)`

Selects a numerical precision type of the explicit dynamics analysis.

## Parameters

**key**

Number or name identifying numerical precision to be used.

0 or SINGLE - Select single precision version of LS-DYNA (default).

1 or DOUBLE - Select double precision version of LS-DYNA.

STAT - Check the status of the numerical precision in effect.

## Notes

Sets the single or double precision version of LS-DYNA into effect. Please check the availability of the double precision version of LS- DYNA on your system before using the command. If it is not available, use the command default.

The double precision version may be up to 20% slower than the single precision version. The results may also vary based on problem specifications.

In addition to EDDBL,STAT, you can use the GUI dialog box to verify which precision version is currently chosen. The GUI is based on the database and is updated to reflect changes.

See Double Precision LS-DYNA for more information.

This command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
