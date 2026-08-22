---
apdl: "DSYM"
method: dsym
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_constraints.FeConstraints.dsym
generated: 2026-08-22
tags: [mapdl-command]
---

# DSYM

PyMAPDL: `mapdl.dsym(lab='', normal='', kcn='', **kwargs)`

Specifies symmetry or antisymmetry degree-of-freedom constraints on nodes.

## Parameters

**lab**

Symmetry label:

- `SYMM` - Generate symmetry constraints as described below (default).
- `ASYM` - Generate antisymmetry constraints as described below.

**normal**

Surface orientation label to determine the constraint set (surface is assumed to be perpendicular to this coordinate direction in coordinate system `KCN` ):

- `X` - Surface is normal to coordinate X direction (default). Interpreted as R direction for non- Cartesian coordinate systems.
- `Y` - Surface is normal to coordinate Y direction. θ direction for non-Cartesian coordinate systems.
- `Z` - Surface is normal to coordinate Z direction. Φ direction for spherical or toroidal coordinate systems.

**kcn**: Reference number of global or local coordinate system used to define surface orientation.

## Notes

Specifies symmetry or antisymmetry degree-of-freedom constraints on the selected nodes. The nodes are first automatically rotated (any previously defined rotations on these nodes are redefined) into coordinate system `KCN`, then zero-valued constraints are generated, as described below, on the selected degree-of-freedom set (limited to displacement, velocity, and magnetic degrees of freedom) ( [[dofsel|DOFSEL]] ). Constraints are defined in the (rotated) nodal coordinate system, as usual. See the [[d|D]] and [[nrotat|NROTAT]] commands for additional details about constraints and nodal rotations.

This command is also valid in PREP7.

Symmetry or antisymmetry constraint generations are based upon the valid degrees of freedom in the model, that is, the de grees of freedom associated with the elements attached to the nodes. The labels for degrees of freedom used in the generation depend on the `Normal` label.

For displacement degrees of freedom, the constraints generated are:

(table not available in the PyMAPDL source, see the Ansys help page)

For velocity degrees of freedom, the constraints generated are:

(table not available in the PyMAPDL source, see the Ansys help page)

For the 2D vector magnetic degree of freedom, AZ, symmetry is naturally satisfied and the SYMM label generates no constraints. The ASYM label generates flux parallel conditions (flux flows parallel to the surface).

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DSYM.html
