---
apdl: "MOVE"
method: move
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.move
generated: 2026-08-22
tags: [mapdl-command]
---

# MOVE

PyMAPDL: `mapdl.move(node='', kc1='', x1='', y1='', z1='', kc2='', x2='', y2='', z2='', **kwargs)`

Calculates and moves a node to an intersection.

## Parameters

**node**: Move this node. If `NODE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE`.

**kc1**: First coordinate system number. Defaults to 0 (global Cartesian).

**x1**, **y1**, **z1**: Input one or two values defining the location of the node in this coordinate system. Input "U" for unknown value(s) to be calculated and input "E" to use an existing coordinate value. Fields are R1, θ1, Z1 for cylindrical, or R1, θ1, Φ1 for spherical or toroidal.

**kc2**: Second coordinate system number.

**x2**, **y2**, **z2**: Input two or one value(s) defining the location of the node in this coordinate system. Input "U" for unknown value(s) to be calculated and input "E" to use an existing coordinate value. Fields are R2, θ2, Z2 for cylindrical, or R2, θ2, Φ2 for spherical or toroidal.

## Notes

Calculates and moves a node to an intersection location. The node may have been previously defined (at an approximate location) or left undefined (in which case it is internally defined at the [[source|SOURCE]] location). The actual location is calculated from the intersection of three surfaces (implied from three coordinate constants in two different coordinate systems). The three (of six) constants easiest to define should be used. The program will calculate the remaining three coordinate constants. All arguments, except `KC1`, must be input. Use the repeat command ( `*REPEAT` ) after the **MOVE** command to define a line of intersection by repeating the move operation on all nodes of the line.

Surfaces of constant value are implied by some commands by specifying a single coordinate value. Implied surfaces are used with various commands ( **MOVE**, [[kmove|KMOVE]], [[nsel|NSEL]], etc.). Three surfaces are available with each of the four coordinate system types. Values or X, Y, or Z may be constant for the Cartesian coordinate system; values of R, θ, or Z for the cylindrical system; and values of R, θ, Φ for the spherical and toroidal systems. For example, an X value of 3 represents the Y-Z plane (or surface) at X=3. In addition, the parameters for the cylindrical and spherical coordinate systems may be adjusted ( [[cs|CS]], [[local|LOCAL]] ) to form elliptical surfaces. For surfaces in elliptical coordinate systems, a surface of "constant" radius is defined by the radius value at the X-axis. Surfaces of constant value may be located in local coordinate systems ( [[local|LOCAL]], [[clocal|CLOCAL]], [[cs|CS]], or [[cskp|CSKP]] ) to allow for any orientation.

The intersection calculation is based on an iterative procedure (250 iterations maximum) and a tolerance of 1.0E-4. The approximate location of a node should be sufficient to determine a unique intersection if more than one intersection point is possible. Tangent "intersections" should be avoided. If an intersection is not found, the node is placed at the last iteration location.

This command is also valid in the [[slashmap|/MAP]] processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MOVE.html
