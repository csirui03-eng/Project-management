---
apdl: "CHECK"
method: check
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.database.Database.check
generated: 2026-08-22
tags: [mapdl-command]
---

# CHECK

PyMAPDL: `mapdl.check(sele='', levl='', **kwargs)`

Checks current database items for completeness.

## Parameters

**sele**

Specifies which elements are to be checked:

- `(blank)` - Check all data.
- `ESEL` - Check only elements in the selected set and unselect any elements not producing geometry check messages. The remaining elements (those producing check messages) can then be displayed and corrected. A null set results if no elements produce a message. Issue [[esel|ESEL]],ALL to select all elements before proceeding.

**levl**

Used only with `Sele` = ESEL:

- `WARN` - Select elements producing warning and error messages.
- `ERR` - Select only elements producing error messages (default).

## Notes

This command will not work if [[shpp|SHPP]],OFF has been set. A similar, automatic check of all data is done before the solution begins.

If the Check Elements option is invoked through the GUI (menu path Main Menu\> Preprocessor\> Meshing\> Check Elems ), the **CHECK**,ESEL logic is used to highlight elements in the following way: good elements are blue, elements having warnings are yellow, and bad (error) elements are red. The currently selected set of elements is not changed by this GUI function.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CHECK.html
