---
apdl: "IRLIST"
method: irlist
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.listing.Listing.irlist
generated: 2026-08-22
tags: [mapdl-command]
---

# IRLIST

PyMAPDL: `mapdl.irlist(**kwargs)`

Prints inertia relief summary table.

## Notes

Prints the inertia relief summary data, including the mass summary table, the total load summary table, and the inertia relief summary table resulting from the inertia relief calculations. These calculations are performed in the solution phase ( [[solve|SOLVE]] ) as specified by the [[irlf|IRLF]] or [[airl|AIRL]] command.

Inertia relief output is stored in the database rather than in the results file ( `Jobname.RST` ). When you issue **IRLIST** or [[airl|AIRL]], Mechanical APDL pulls the information from the database, which contains the inertia relief output from the most recent solution ( [[solve|SOLVE]] ).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_IRLIST.html
