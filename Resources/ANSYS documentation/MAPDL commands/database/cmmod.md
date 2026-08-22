---
apdl: "CMMOD"
method: cmmod
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.components.Components.cmmod
generated: 2026-08-22
tags: [mapdl-command]
---

# CMMOD

PyMAPDL: `mapdl.cmmod(cname='', keyword='', value='', **kwargs)`

Modifies the specification of a component.

## Parameters

**cname**: Name of the existing component or assembly to be modified.

**keyword**

The label identifying the type of value to be modified.

- NAME - Modify the NAME of the component

**value**: If `Keyword` is NAME, then the value is the alphanumeric label to be applied. See the [[cm|CM]] command for naming convention details. If a component named `Value` already exists, the command will be ignored and an error message will be generated.

## Notes

The naming conventions for components, as specified in the [[cm|CM]] command, apply for **CMMOD** ( 256 characters, "ALL", "STAT" and "DEFA" are not allowed, etc.). However, if you choose a component name that is already designated for another component, an error message will be issued and the command will be ignored.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMMOD.html
