---
apdl: "DFSWAVE"
method: dfswave
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.dfswave
generated: 2026-08-22
tags: [mapdl-command]
---

# DFSWAVE

PyMAPDL: `mapdl.dfswave(kcn='', radius='', psdref='', dens='', sonic='', incang='', npara='', sampopt='', **kwargs)`

Specifies the incident planar waves with random phases for a diffuse sound field.

## Parameters

**kcn**

Local coordinate system:

- `N` - Coordinate system number. Default = 0.
- `DELETE` - Delete defined incident diffused planar waves.

**radius**: Radius of the reference sphere on which the incident planar waves are distributed with equal energy. Defaults to 50 x the half-maximum dimension of the structural panel.

**psdref**: Reference power spectral density. Default = 1.

**dens**: Mass density of incident planar wave media. Default = 1.2041 kg/m <sup>3</sup>.

**sonic**: Sound speed in incident planar wave media. Default = 343.24 m/s)

**incang**: Maximum incident angle (0 <sup>o</sup> \<= `degree` \<= 180 <sup>o</sup> ) against the positive z axis in the local coordinate system `KCN`. Default = 89 <sup>o</sup>.

**npara**: Number of divisions on the reference sphere with cutting planes parallel to the x-y coordinate plane of the local coordinate system. Default = 20.

**sampopt**

Random sampling option:

- `ALL` - Initializes the random generator of incident planar wave phases and samples the phases at each solving frequency.
- `MULT` - Initializes the random generator of incident planar wave phases at the first frequency and samples the phases at each solving frequency.
- `MONO` - Initializes the random generator of incident planar wave phases and samples the phases only once at first solving frequency so that the same phases are used over the whole frequency range for each incident planar wave.

## Notes

Issue the **DFSWAVE** command to activate a diffuse sound field. (The [[awave|AWAVE]] command does not activate a diffuse sound field.)

The `SURF154` surface element must be defined on the surface of the structural solid element for the excitation.

The acoustic elements and the absorbing boundary condition must be defined in the open acoustic domain. Do not define the acoustic domain on the excitation side.

The [[pras|PRAS]] and [[plas|PLAS]] commands calculate the average transmission loss for multiple sampling phases at each frequency over the frequency range.

The symmetry of a panel structure cannot be used to reduce the simulation size, as the incident plane waves have varying random phase angles. The z axis of the Cartesian coordinate system ( `KCN` ) must be consistent with the panel's outward normal unit vector at the center of the panel's sending side.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DFSWAVE.html
