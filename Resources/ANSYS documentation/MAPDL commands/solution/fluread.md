---
apdl: "FLUREAD"
method: fluread
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.fluread
generated: 2026-08-22
tags: [mapdl-command]
---

# FLUREAD

PyMAPDL: `mapdl.fluread(fname='', ext='', kdim='', kout='', limit='', listopt='', **kwargs)`

Reads one-way Fluent-to-Mechanical APDL coupling data via a `.cgns` file with one-side fast Fourier transformation complex pressure peak value.

## Parameters

**fname**: File name and directory path of a one-way Fluent-to-Mechanical APDL coupling data file (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. Defaults to `jobname`.

**ext**: File name extension of the one-way Fluent-to-Mechanical APDL coupling data file. Defaults to `.cgns` ).

**kdim**: Interpolation data for mapping. A value of 0 (default) or 2 applies 2D interpolation (where interpolation occurs on a surface).

**kout**

Outside region results for mapping:

- `0` - Use the value(s) of the nearest region point for points outside of the region. This behavior is the default.
- `1` - Set results extrapolated outside of the region to zero.

**limit**

Number of nearby nodes considered for mapping interpolation. Minimum = 5. Default = 20.

Lower values reduce processing time; however, some distorted or irregular meshes require a higher value in cases where three nodes are encountered for triangulation.

**listopt**

Type of items picked:

- `(blank)` - No listing (default).
- `SOURCE` - List the node coordinates and complex pressure values on the Fluent source side during the solution.
- `TARGET` - List the node coordinates and complex pressure values on the mapped Mechanical APDL target side during the solution.
- `BOTH` - List the node coordinates and complex pressure values on both the Fluent source side and the mapped Mechanical APDL target side during the solution.

## Notes

The **FLUREAD** command reads one-way Fluent-to-Mechanical APDL coupling data from a `.cgns` file. The Fluent one-side fast Fourier transformation (FFT) peak complex pressure values are mapped to the Mechanical APDL structure model during the acoustic-structural solution at each FFT frequency.

The command can be used only for the model with the acoustic elements.

To apply complex pressure to the structure model, define the `SURF154` surface element, then define the one-way coupling interface ( [[sf|SF]],,FSIN) on the element.

You can define the solving frequency range via the `HARFRQ` command. The solver selects the FFT frequencies between the beginning and ending frequencies. The number of substeps is determined by the number of FFT frequencies over the frequency range. The number of substeps defined via the [[nsubst|NSUBST]] command is overwritten.

For better mapping performance, consider the following:

- Calculations for out-of-bound points require much more processing time than do points that are within bounds.
- For each point in the structural destination mesh, the command searches all possible triangles in the Fluent source mesh to find the best triangle containing each point, then performs a linear interpolation inside this triangle. For faster and more accurate results, consider your interpolation method and search criteria carefully. (See `LIMIT`.)

It is possible to apply one-way coupling excitation to multiple frequencies. The one-side FFT peak complex pressure values are necessary to do so.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FLUREAD.html
