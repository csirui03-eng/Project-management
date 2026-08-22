---
apdl: "CGLOC"
method: cgloc
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.inertia.Inertia.cgloc
generated: 2026-08-22
tags: [mapdl-command]
---

# CGLOC

PyMAPDL: `mapdl.cgloc(xloc='', yloc='', zloc='', **kwargs)`

Specifies the origin location of the acceleration coordinate system.

## Parameters

**xloc**, **yloc**, **zloc**: Global Cartesian X, Y, and Z coordinates of the acceleration coordinate system origin.

## Notes

Specifies the origin location of the acceleration coordinate system with respect to the global Cartesian system. The axes of this acceleration coordinate system are parallel to the global Cartesian axes.

A structure may be rotating about the global Cartesian origin ( [[omega|OMEGA]], [[domega|DOMEGA]] ), which may in turn be rotating about another point (the origin of the acceleration coordinate system), introducing Coriolis effects. The location of this point (relative to the global Cartesian origin) is specified with this **CGLOC** command. For example, if Y is vertical and the global system origin is at the surface of the earth while the acceleration system origin is at the center of the earth, `YLOC` should be -4000 miles (or equivalent) if the rotational effects of the earth are to be included. The rotational velocity of the global Cartesian system about this point is specified with the [[cgomga|CGOMGA]] command, and the rotational acceleration is specified with the [[dcgomg|DCGOMG]] command.

The rotational velocities and accelerations are mainly intended to include mass effects in a static ( [[antype|ANTYPE]],STATIC) analysis. If used in dynamic analyses, no coupling exists between the user input terms and the time history response of the structure. See [Acceleration Effect](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool1.html#) [[acel|ACEL]], [[cgomga|CGOMGA]], [[dcgomg|DCGOMG]], [[domega|DOMEGA]], and [[omega|OMEGA]].

See [Analysis Tools](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/str_EnMoinStAn.html)

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CGLOC.html
