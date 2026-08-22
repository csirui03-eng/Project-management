---
apdl: "PMLOPT"
method: pmlopt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.artificially_matched_layers.ArtificiallyMatchedLayers.pmlopt
generated: 2026-08-22
tags: [mapdl-command]
---

# PMLOPT

PyMAPDL: `mapdl.pmlopt(psys='', lab='', xminus='', xplus='', yminus='', yplus='', zminus='', zplus='', woptxm='', woptxp='', woptym='', woptyp='', woptzm='', woptzp='', **kwargs)`

Defines perfectly matched layers (PMLs) or irregular perfectly matched layers (IPML).

## Parameters

**psys**: PML element coordinate system number. `PSYS` may be 0 (global Cartesian) or any previously defined local Cartesian coordinate system number (\>10). Defaults to 0. (Not used for IPML.)

**lab**

Label defining the number of dimensions (not used for IPML) :

- `ONE` - A one-dimensional PML region.
- `THREE` - A three-dimensional PML region (default).

**xminus**: For PML, normal reflection coefficient (harmonic analysis) or attenuation factor (static structural analysis) in negative X direction of `PSYS`. Defaults to 1.E-3 (equivalent to -60 dB) for `WOptXm` = PROP or HYBR, 30 for `WOptXm` = EVAN, and 40 for `WOptXm` = MAXP.

**xplus**: Normal reflection coefficient (harmonic analysis) or attenuation factor (static structural analysis) in positive X direction of `PSYS`. Defaults to 1.E-3 (equivalent to -60 dB) for `WOptXp` = PROP or HYBR, 30 for `WOptXp` = EVAN, and 40 for `WOptXp` = MAXP. (Not used for IPML.)

**yminus**: Normal reflection coefficient (harmonic analysis) or attenuation factor (static structural analysis) in negative Y direction of `PSYS`. Defaults to 1.E-3 (equivalent to -60 dB) for `WOptYm` = PROP or HYBR, 30 for `WOptYm` = EVAN, and 40 for `WOptYm` = MAXP. (Not used for IPML.)

**yplus**: Normal reflection coefficient (harmonic analysis) or attenuation factor (static structural analysis) in positive Y direction of `PSYS`. Defaults to 1.E-3 (equivalent to -60 dB) for `WOptYp` = PROP or HYBR, 30 for `WOptYp` = EVAN, and 40 for `WOptYp` = MAXP. (Not used for IPML.)

**zminus**: Normal reflection coefficient (harmonic analysis) or attenuation factor (static structural analysis) in negative Z direction of `PSYS`. Defaults to 1.E-3 (equivalent to -60 dB) for `WOptZm` = PROP or HYBR, 30 for `WOptZm` = EVAN, and 40 for `WOptZm` = MAXP. (Not used for IPML.)

**zplus**: Normal reflection coefficient (harmonic analysis) or attenuation factor (static structural analysis) in positive Z direction of `PSYS`. Defaults to 1.E-3 (equivalent to -60 dB) for `WOptZp` = PROP or HYBR, 30 for `WOptZp` = EVAN, and 40 for `WOptZp` = MAXP. (Not used for IPML.)

**woptxm**, **woptxp**, **woptym**, **woptyp**, **woptzm**, **woptzp**

Type of attenuated wave in the PML region in each direction:

- `PROP` - Only the propagating wave is attenuated. The PML parameter is set to s = 1-jβ in harmonic analyses and acoustic transient analyses.
- `EVAN` - Only the evanescent field is attenuated. The PML parameter is set to s = α ( α \> 1) in static analyses.
- `HYBR` - Both the propagating wave and the evanescent wave are attenuated (default). The PML parameter is set to s = α -jβ ( α \> 1). The program sets the coefficient α values in terms of the normal reflection coefficients in harmonic analyses.
- `MAXP` - The maximum attenuation coefficient for frequency-independent PML parameter in harmonic analyses, acoustic modal analyses, and acoustic transient analyses.

## Notes

The **PMLOPT** command can be used to define perfectly matched layers (PML). The following element types support perfectly matched layers:

- Acoustic elements: `FLUID30`, `FLUID220`, and `FLUID221` (KEYOPT(4) \> 0) in a modal, harmonic, or transient acoustic analysis.
- Piezoelectric coupled-field elements: `PLANE222`, `PLANE223`, `SOLID225`, `SOLID226`, and `SOLID227` (KEYOPT(15) = 1) in a harmonic piezoelectric analysis. For the lower order elements ( `PLANE222` and `SOLID225` ), PML is only supported with the B-bar method.
- Structural elements: `PLANE182`, `PLANE183`, `SOLID185`, `SOLID186`, and `SOLID187` (KEYOPT(15) = 1) in a linear static or harmonic structural analysis. For the lower order elements ( `PLANE182` and `SOLID185` ), PML is only supported with the B-bar method.

Each PML region must have a uniquely defined PML element coordinate system ( [[psys|PSYS]] ). Normal reflection coefficient values for a harmonic analysis must be less than 1.

The **PMLOPT** command can also be used to define irregular perfectly matched layers (IPML) for acoustic analyses. Normal reflection coefficient values for a harmonic analysis must be less than 1.

Issue **PMLOPT**,STAT to list the current normal reflection coefficient or attenuation factor settings for a PML or IPML region. Issue **PMLOPT**,CLEAR to clear all normal reflection coefficient settings and restore them to the defaults.

Issue **PMLOPT**,PSYS,CLEAR to clear all normal reflection coefficient settings for the specified PML element coordinate system and restore them to the defaults.

For modal analysis, use one buffer element between the PML and the resonant structure to avoid the spurious modes. The mode patterns should be evaluated graphically.

See [Artificially Matched Layers](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_acous/acous_artificial.html#acous_aml)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PMLOPT.html
