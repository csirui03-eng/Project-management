---
apdl: "EDBX"
method: edbx
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edbx
generated: 2026-08-22
tags: [mapdl-command]
---

# EDBX

PyMAPDL: `mapdl.edbx(option='', boxid='', xmin='', xmax='', ymin='', ymax='', zmin='', zmax='', **kwargs)`

Creates a box shaped volume to be used in a contact definition for

explicit dynamics.

## Parameters

**option**

Label identifying the contact box definition option to be performed.

ADD - Adds a contact box definition (default).

DELETE - Deletes a contact box definition.

LIST - Lists each box ID number, and the coordinates that make up each box shaped  
volume.

**boxid**: User defined list ID number.

**xmin**: Minimum x-coordinate.

**xmax**: Maximum x-coordinate.

**ymin**: Minimum y-coordinate.

**ymax**: Maximum y-coordinate.

**zmin**: Minimum z-coordinate.

**zmax**: Maximum z-coordinate.

## Notes

The ANSYS LS-DYNA command EDCGEN allows you to define contact and target volumes using box ID numbers BOXID1 and BOXID2, respectively. If you use these arguments to define contact volumes, you must first define their coordinates using the EDBX command.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
