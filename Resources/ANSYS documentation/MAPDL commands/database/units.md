---
apdl: "/UNITS"
method: units
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.set_up.SetUp.units
generated: 2026-08-22
tags: [mapdl-command]
---

# /UNITS

PyMAPDL: `mapdl.units(label='', lenfact='', massfact='', timefact='', tempfact='', toffst='', chargefact='', forcefact='', heatfact='', **kwargs)`

Annotates the database with the system of units used.

## Parameters

**label**

Label to denote the system of units used in this job:

- `USER` - User-defined system (default).
- `SI` - International system (m, kg, s, K).
- `MKS` - MKS system (m, kg, s, °C).
- `uMKS` - μMKS system (μm, kg, s, °C).
- `CGS` - CGS system (cm, g, s, °C).
- `MPA` - MPA system (mm, Mg, s, °C).
- `BFT` - U. S. Customary system using feet (ft, slug, s, °F).
- `BIN` - U. S. Customary system using inches (in, lbf2s <sup>2</sup> /in, s, °F).

**lenfact**, **massfact**, **timefact**, **tempfact**, **toffst**, **chargefact**, **forcefact**, **heatfact**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_UNITS.html) for further information.

## Notes

Allows the user to set a marker in the database indicating the system of units used. The setting may be reviewed with the [[slashstatus|/STATUS]] command at the Begin level. The units label and conversion factors on this command are for user convenience only and have no effect on the analysis or data. That is, **/UNITS** will not convert database items from one system to another (for example, from U. S. Customary to SI, etc.). The units setting will be written to the file of IGES data \[ [[igesout|IGESOUT]] or [[cdwrite|CDWRITE]] \], which can then be read by many programs that read IGES files. The user must still use consistent units for the results to be valid.

If you choose the MKS system of units, the EPZRO option for the [[emunit|EMUNIT]] command is set to 8.85 e-12 F/m. (EPZRO specifies alternate free-space permittivity.)

For micro-electromechanical systems (MEMS), where dimensions are on the order of microns, see the conversion factors in [System of Units](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cou/Hlp_G_COU1_3.html#couthermelesmksvfa) in the [Coupled-Field Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cou/Hlp_G_COU_N4.html).

If you use the Mechanical APDL ADAMS Interface to export model information to the ADAMS program, the **/UNITS** command is required to ensure the correct transfer of data between Mechanical APDL and ADAMS. You can choose a predefined unit system label ( `Label` = SI, CGS, etc.) or you can select the user-defined system option ( `Label` = USER) and input the appropriate conversion factors ( `LENFACT`, `MASSFACT`, `TIMEFACT`, and `FORCEFACT` ). The conversion factors are written to the ADAMS input file `Jobname.MNF` to correctly generate the load. For more information, see [Export to ADAMS](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/advexad.html#advverres12902).

All differences between the base solution units used by the Mechanical APDL and CFX solvers are noted in the Mechanical APDL output file. Unit conversions are applied automatically to all loads transferred unless `Label` = USER. Unit conversions are not applied to any of the loads transferred between the Mechanical APDL and CFX solvers if they use a user-defined unit system.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_UNITS.html
