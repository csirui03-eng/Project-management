---
apdl: "PLTRAC"
method: pltrac
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.trace_points.TracePoints.pltrac
generated: 2026-08-22
tags: [mapdl-command]
---

# PLTRAC

PyMAPDL: `mapdl.pltrac(analopt='', item='', comp='', trpnum='', name='', mxloop='', toler='', escl='', mscl='', **kwargs)`

Displays a charged particle trace on an element display.

## Parameters

**analopt**

Analysis option

- `ELEC` - Particle trace in electric field
- `MAGN` - Particle trace in magnetic field
- `EMAG` - Particle trace in presence of both electric and magnetic fields (default)

**item**: Label identifying the item to be contoured. Valid item labels are shown in *PLTRAC - Valid Item and Component Labels* below. Some items also require a component label. If `Item` is blank, display only the path trajectory.

**comp**: Component of the item (if required). Valid component labels are shown in *PLTRAC - Valid Item and Component Labels* below.

**trpnum**: Trace point number for storing trajectory data for use with [[path|PATH]] logic. Defaults to 0 (no trajectory path data is stored for further processing with [[path|PATH]] logic).

**name**: Name of prefix of array variable. Defaults to TRAC. `Name` POIN stores trajectory path points for trace point number `TRPNum`. If `Analopt` = ELEC, MAGN, or EMAG, two additional array parameters, `Name` DATA and `Name` LABL, store trajectory path data and labels for the same `TRPNum`.

**mxloop**: Maximum number of loops traced by a particle. Defaults to 1000.

**toler**: Length tolerance used for particle trajectory geometry calculation. Valid for `Analopt` = ELEC, MAGN, or EMAG. If particle trace appears to terminate inside an element, adjusting the length tolerance may be necessary. Defaults to 1.0 x 10 <sup>-8</sup>.

**escl**: Electric field scale factor. Setting this scale factor affects only the tracing, not the field solution results. A negative factor corresponds to the opposite vector direction. Valid only for `Analopt` = ELEC or EMAG. Defaults to 1.

**mscl**: Magnetic field scale factor. Setting this scale factor affects only the tracing, not the field solution results. A negative factor corresponds to the opposite vector direction. Valid only for `Analopt` = MAGN or EMAG. Defaults to 1.

## Notes

For a specified item, the variation of the item is displayed along the particle trace as a color- contoured ribbon. The [[trpoin|TRPOIN]] command must be used to define a point on the trajectory path. Multiple traces may be displayed simultaneously by defining multiple trace points. Issue the [[trplis|TRPLIS]] command to list the current tracing points. Issue the [[trpdel|TRPDEL]] command to delete tracing points defined earlier. Use the [[paput|PAPUT]] command with the POIN option to retrieve the particle trajectory points as path points.

The model must be 3D for the ELEC, MAGN, and EMAG analysis options.

Three array parameters are created at the time of the particle trace: TRACPOIN, TRACDATA and TRACLABL. These array parameters can be used to put the particle velocity and the elapsed time into path form. The procedure to put the arrays into a path named PATHNAME is as follows:

``` apdl
*get,npts,PARM,TRACPOIN,DIM,x
PATH,PATHNAME,npts,9,1
PAPUT,TRACPOIN,POINTS
PAPUT,TRACDATA,TABLES
PAPUT,TRACLABL,LABELS
PRPATH,S,T_TRACE,VX_TRACE,VY_TRACE,VZ_TRACE,VS_TRACE
```

If working in the GUI, use the "All information" option to retrieve information from all three arrays at once.

### PLTRAC - Valid Item and Component Labels

| Item | Comp | Description |
|----|----|----|
| **Valid item labels for** `Analopt` = ELEC nodal results are: |  |  |
| VOLT |  | Electric potential. |
| **Valid item labels for** `Analopt` = MAGN or EMAG nodal results are: |  |  |
| None |  | Color contour displayed. |

See the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for more information on charged particle traces. See [Animation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS15_7.html) in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for information on particle trace animation.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLTRAC.html
