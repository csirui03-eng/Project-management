---
apdl: "WPCSYS"
method: wpcsys
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.working_plane.WorkingPlane.wpcsys
generated: 2026-08-22
tags: [mapdl-command]
---

# WPCSYS

PyMAPDL: `mapdl.wpcsys(wn='', kcn='', **kwargs)`

Defines the working plane location based on a coordinate system.

## Parameters

**wn**: Window number whose viewing direction will be modified to be normal to the working plane (defaults to 1). If `WN` is a negative value, the viewing direction will not be modified.

**kcn**: Coordinate system number. `KCN` may be 0,1,2 or any previously defined local coordinate system number (defaults to the active system).

## Notes

Defines a working plane location and orientation based on an existing coordinate system. If a Cartesian system is used as the basis ( `KCN` ) for the working plane, the working plane will also be Cartesian, in the X-Y plane of the base system. If a cylindrical, spherical, or toroidal base system is used, the working plane will be a polar system in the R-θ plane of the base system.

If working plane tracking has been activated ( [[csys|CSYS]],WP or [[csys|CSYS]],4), the updated active coordinate system will be of a similar type, except that a toroidal system will be updated to a cylindrical system. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for more information on working plane tracking.

This command is valid in any processor.

Some primitive generation commands will not honor R-theta transformations for non-cartesian coordinate systems. Refer to the primitive commands table for more information.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_WPCSYS.html
