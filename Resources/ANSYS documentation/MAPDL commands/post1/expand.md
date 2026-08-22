---
apdl: "EXPAND"
method: expand
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.expand
generated: 2026-08-22
tags: [mapdl-command]
---

# EXPAND

PyMAPDL: `mapdl.expand(nrepeat='', modal='', hindex='', icsys='', sctang='', phase='', **kwargs)`

Displays the results of a modal cyclic symmetry analysis.

## Parameters

**nrepeat**: Number of sector repetitions for expansion. The default is 0 (no expansion).

**modal**: Specifies that the expansion is for a modal cyclic symmetry analysis.

**hindex**: The harmonic index ID for the results to expand.

**icsys**: The coordinate system number used in the modal cyclic symmetry solution. The default is the global cylindrical coordinate system (specified via the [[csys|CSYS]] command where `KCN` = 1).

**sctang**: The sector angle in degrees, equal to 360 divided by the number of cyclic sectors.

**phase**: The phase angle in degrees to use for the expansion. The default is 0. Typically, the value is the peak displacement (or stress/strain) phase angle obtained via the [[cycphase|CYCPHASE]] command.

## Notes

Issue this command to display the results of a modal cyclic symmetry analysis.

When you issue the **EXPAND**, `Nrepeat` command, subsequent [[set|SET]] commands read data from the results file and expand them to `Nrepeat` sectors. As long as no entities have been modified, this expansion can be negated (that is, reverted to single sector) by issuing **EXPAND** with no arguments. If you modify entities and wish to return to the partial model, use the Session Editor (see Restoring Database Contents in the [Operations Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ope/Hlp_G_OPE8.html)).

**EXPAND** displays the results and allows you to print them, as if for a full model. The harmonic index (automatically retrieved from the results file) appears in the legend column.

When plotting or printing element strain energy (SENE), the **EXPAND** command works with brick or tet models only. Element kinetic energy (KENE) plotting or printing is not supported.

**EXPAND** is a specification command valid only in POST1. It is significantly different from the [[cycexpand|/CYCEXPAND]] command in several respects, (although you can use either command to display the results of a modal cyclic symmetry analysis):

- **EXPAND** has none of the limitations of the [[cycexpand|/CYCEXPAND]] command.
- **EXPAND** changes the database by modifying the geometry, the nodal displacements, and element stresses as they are read from the results file, whereas the [[cycexpand|/CYCEXPAND]] command does not change the database.

> [!WARNING]
> The **EXPAND** command creates new nodes and elements; therefore, saving (or issuing the `/EXIT`, ALL command) after issuing the **EXPAND** command can result in large databases.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EXPAND.html
