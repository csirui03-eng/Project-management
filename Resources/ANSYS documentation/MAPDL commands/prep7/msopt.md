---
apdl: "MSOPT"
method: msopt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.msopt
generated: 2026-08-22
tags: [mapdl-command]
---

# MSOPT

PyMAPDL: `mapdl.msopt(option='', sname='', value1='', value2='', value3='', value4='', value5='', value6='', value7='', **kwargs)`

Specifies solution options for a [multistage cyclic symmetry analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/ans_mstag_introTheory.html).

## Parameters

**option**

Multistage cyclic symmetry analysis option. There is no default. You must choose one of the following options:

- `CSYS` - Activates a previously defined cyclic coordinate system by the reference number specified in `Value1`. `Sname` is ignored. This option is only valid in the /PREP7 processor.

  - `Value1` - Cylindrical coordinate system reference number. You must have already created the coordinate system by issuing prior commands like [[cs|CS]] or [[local|LOCAL]] to define it. Defaults to 1 where the global Cartesian Z axis is the cyclic symmetry axis.

  You must define the coordinate system before defining the stages.

- `NEW` - Creates a new stage with the name entered in `Sname` and the `Value1` - `Value6` specifications listed in the table below. This option is only valid in the /PREP7 processor.

  - `Sname` - An alphanumeric name used to identify the stage. `Sname` may be up to 32 characters, beginning with a letter and containing only letters, numbers, and underscores. Names beginning with an underscore (for example, LOOP) are reserved for use by Mechanical APDL and should be avoided. The component name ALL is not permitted.

  (table not available in the PyMAPDL source, see the Ansys help page)

  When creating a new stage, the base and duplicate sector meshes should be coincident. The offset between the number of base and duplicate coincident nodes is constant throughout the whole model. The same is true for the element numbers.

- `DELETE` - Deletes the stage identified by `Sname`.

  - `Sname` - The name of the stage to be deleted. Entities such as nodes and elements contained in the stage are unaffected. Only the grouping and the related constraint equations are concerned.

- `EXPAND` - Specifies stages (identified by `Sname` ) and sectors (sector number specified in `Value1` ) for subsequent expansion. This option is only valid in the /POST1 processor.

  - `Sname` - The name of the stage to be expanded. A value of 0 resets all expansion settings. A value of ALL means all existing stages will be expanded (default).
  - `Value1` - The sector number. A value of 0 resets all sector settings. A value of ALL means all sectors will be expanded (default).

- `LIST` - Lists the stage identified by `Sname` with the level of detail specified in `Value1`.

  - `Sname` - The name of the stage to be listed. If blank, list all stages (default).
  - `Value1` - Key for specifying the level of detail.
    - `0 (, or OFF)` - Basic listing (default).
    - `1 (, or ON)` - Detailed listing, including constraint equations information. Note that the interstage constraint equations number information is only listed for the stage with the smallest number of sectors.

- `MODIFY` - Sets the [harmonic index](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycmodalans.html#harmindex) of a stage identified by `Sname` to the integer specified in `Value1`.

  - `Sname` - The name of the stage to be modified.
  - `Value1` - The new [harmonic index](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycmodalans.html#harmindex). Existing cyclic and multistage interface constraint equations will be deleted.

- `RESET` - Deletes all stages and resets all multistage analysis settings.

**sname**, **value1**, **value2**, **value3**, **value4**, **value5**, **value6**, **value7**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MSOPT.html) for further information.

## Notes

The **MSOPT** command is used to specify solution options for a [multistage cyclic symmetry analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/ans_mstag_introTheory.html). It is not part of the [[cyclic|CYCLIC]] procedure for a cyclic symmetry analysis.

When you issue **MSOPT**,EXPAND, subsequent [[set|SET]] commands read the data set from the specified `.rst` file and expand the nodes and elements to the stages and sectors specified via **MSOPT**,EXPAND.

**Example Usage** [Example: Static Analysis of a Compressor Model with 4 Axial Stages Without a Duplicate Sector](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/multistage_ex_compressor.html#)

[Example: Linear Perturbation Modal Analysis of a Simplified Model with 2 Axial Stages and a Non- planar Interstage Boundary](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/multistag_ex_linearPert.html#)

[Example: Modal Analysis of Turbomachinery Stage Modeled as 2 Radial Stages with Offset Cyclic Edge Starting Points](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/multistag_ex_modal_turboOffset.html#)

[Example: Mutistage Multiharmonic Modal Analysis of a Hollow Cylinder Modeled Using 2 Stages](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/mstag_hollowCyl2stages.html#)

[Example: Multiharmonic Linear Perturbation Modal Analysis of a Simplified Model with 3 Axial Stages](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mstag/ans_mstagExMultiHarmLP.html#)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MSOPT.html
