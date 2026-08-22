---
apdl: "ANSTOAQWA"
method: anstoaqwa
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.files.Files.anstoaqwa
generated: 2026-08-22
tags: [mapdl-command]
---

# ANSTOAQWA

PyMAPDL: `mapdl.anstoaqwa(fname='', vertaxis='', gc='', rho='', hwl='', diffkey='', symxkey='', symykey='', **kwargs)`

Creates an AQWA-LINE input file from the current Mechanical APDL model.

## Parameters

**fname**: AQWA file name. Defaults to `Jobname`.

**vertaxis**

Axis in the vertical direction:

- `Y (or 2)` - Global Y axis.
- `Z (or 3)` - Global Z axis (default).

**gc**: Gravitational acceleration. Defaults to 9.81.

**rho**: Density of water. Defaults to 1025.0.

**hwl**: Waterline height in model coordinates. Defaults to 0.0.

**diffkey**

Diffracting model key:

- `0` - Create a non-diffracting AQWA model.
- `1` - Create a diffracting AQWA model (default).

**symxkey**

Key indicating if model is symmetric about the global XZ plane:

- `0` - No symmetry about XZ plane (default).
- `1` - Use symmetry about XZ plane. Only include (or select) half the model.

**symykey**

Key indicating if model is symmetric about the global YZ plane:

- `0` - No symmetry about YZ plane (default).
- `1` - Use symmetry about YZ plane. Only include (or select) half the model.

## Notes

This command creates the input file `Fname`.aqwa for the Ansys Aqwa Multi-Body Hydrodynamics System for diffraction analysis in AQWA-LINE from the model currently in the database, based on the currently selected set of elements. The selected set must only include the hull envelope; no internal structure should be selected.

There should be a line of nodes defined at the waterline. Only those elements that are entirely below the waterline will be specified as diffracting. If there are no waterline nodes, there will be no diffracting elements at the waterline, which will severely reduce the accuracy of the diffraction analysis.

The translator maps PLANE42, SHELL63, and `SHELL181` elements to PANELs, and maps PIPE16 and PIPE59 elements to TUBEs. It does not recognize any other element types. Any material or geometric properties can be used for the shell elements, as AQWA does not need any properties at all and the command does not use them. All the shell elements below the water must have their normals pointing outward.

TUBE elements in AQWA have material density, outside diameter, wall thickness, added mass, and drag coefficients, so appropriate properties should be used in the Mechanical APDL model. PIPE59 elements can have added mass and damping coefficients; these will be written to the file. The Mechanical APDL program uses the inertia coefficient C<sub>M</sub>, whereas AQWA uses the added mass coefficient C<sub>A</sub>, where C<sub>M</sub> = (1 + C<sub>A</sub> ). This correction is made automatically.

(table not available in the PyMAPDL source, see the Ansys help page)

In AQWA the vertical axis is always the Z-axis. The command can convert a model built with either the Y or Z-axis vertical, but the X-axis must be horizontal and should preferably be along the fore/aft axis of the vessel. If the structure is symmetric and you wish to use the symmetry options, you must only select one half or one quarter of the model, as appropriate. If you model a complete vessel and specify X symmetry, the AQWA model will contain two sets of coincident elements.

If you are working from a model created for a structural analysis, it will probably be necessary to remesh the model as the structural mesh is most likely finer than needed for a diffraction analysis.

If you enter this command interactively (with the GUI active) and no data is provided for the command options, the application prompts you for their values.

You must verify the completeness and accuracy of the data written.

**AQWA-LINE Notes**

The file will specify restart stages 1-2 only. It has no options except REST, so AQWA may fail if any of the elements are badly shaped.

The total mass is obtained by integrating over the wetted surface area and adding the TUBE masses, so it should be reasonably accurate. However, the integration used is not as accurate as that in AQWA, so there may be a small difference between the weight and buoyancy, particularly if tubes represent a large portion of the model.

The position of the CG is unknown. A point mass is placed at the water-line above the CB, but you should change this to the correct position.

The moments of inertia are estimated based on the overall dimensions of the model and using standard formulae for a ship. You should change these to the correct values.

The maximum frequency is calculated from the maximum side length of the underwater elements. The range of frequencies runs from 0.1 rad/s to the calculated maximum, in steps of 0.1 rad/s.

The directions are in steps of 15° over a range that is determined by the symmetry you have specified, in accordance with the requirements of AQWA.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANSTOAQWA.html
