---
apdl: "EDASMP"
method: edasmp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edasmp
generated: 2026-08-22
tags: [mapdl-command]
---

# EDASMP

PyMAPDL: `mapdl.edasmp(option='', asmid='', part1='', part2='', part3='', part4='', part5='', part6='', part7='', part8='', part9='', part10='', part11='', part12='', part13='', part14='', part15='', part16='', **kwargs)`

Creates a part assembly to be used in an explicit dynamic analysis.

## Parameters

**option**

Label identifying the part assembly option to be performed.

ADD - Adds a part assembly (default).

DELETE - Deletes a part assembly.

LIST - Lists each part assembly number, and the part numbers that make up each part  
assembly.

**asmid**: User defined part assembly ID number. The part assembly number cannot be the same as any currently defined part ID number.

**part1, part2, part3, . . . , part16**: Part numbers to be included in the assembly (up to 16 different parts).

## Notes

Several ANSYS LS-DYNA commands (such as EDCGEN, EDPVEL, and EDIS) refer to assembly ID numbers. If you intend to use assembly ID numbers with these commands, you must first define the assembly ID numbers using EDASMP.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
