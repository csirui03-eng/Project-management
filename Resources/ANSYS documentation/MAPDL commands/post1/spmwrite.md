---
apdl: "SPMWRITE"
method: spmwrite
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.spmwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# SPMWRITE

PyMAPDL: `mapdl.spmwrite(method='', nmode='', inputs='', inputlabels='', outputs='', outputlabels='', nic='', velacckey='', fileformat='', **kwargs)`

Calculates the state-space matrices and writes them to the SPM file.

## Parameters

**method**

Reduction method for the calculation of the state-space matrices.

- `MODAL` - Method based on modal analysis results from LANB, LANPCG, SNODE, or SUBSP eigensolver (default).

**nmode**: Number of modes to be used. Defaults to all modes.

**inputs**

Definition of the inputs. Defaults to all load vectors on the MODE file.

If an integer is entered, it specifies the number of load vectors from the MODE file used for the definition of the inputs. The first `Inputs` load vectors are used.

If `Inputs` is an array parameter, the first column is the node number and the second column is the structural degree of freedom (1=UX, 2=UY, 3=UZ, 4=ROTX, 5=ROTY, 6=ROTZ) indicating input points. The number of rows in the array parameter is equal to the number of inputs.

**inputlabels**

Definition of the input labels. Defaults to the load vector numbers or input definition (node and degree of freedom array parameter), depending on the `Inputs` specification.

If a character array parameter is entered (Type=CHAR in the [[dim|*DIM]] command), each 8 character string represents an input label. Only valid when `Inputs` is an array parameter

**outputs**

Definition of the outputs. Defaults to the inputs.

If an array parameter is entered, the first column is the node number and the second column is the structural degree of freedom (1=UX, 2=UY, 3=UZ, 4=ROTX, 5=ROTY, 6=ROTZ) of the output points. The number of rows in the array parameter is equal to the number of outputs.

**outputlabels**

Definition of the output labels. Defaults to the output definition (node and degree of freedom) if used, else defaults to the `InputLabels`.

If a character array parameter is entered (Type=CHAR in the \*DIM command), each 8 character string represents an output label.

**nic**: Load vector on the `MODE` file used for the calculation of the initial conditions. Defaults to no initial condition.

**velacckey**

Output velocities and accelerations key.

- `OFF` - Output displacements only (default).
- `ON` - Output displacements, velocities and accelerations.

**fileformat**

The format of the SPM file.

- `0` - Dense format.
- `1` - Matrix Market Exchange format (non-zero terms only).
- `2` - Twin Builder SML format without reference (default).
- `3` - Twin Builder SML format with common reference.
- `4` - Twin Builder SML format with independent references.

## Notes

The SPMWRITE generates the file `Jobname.SPM` containing the state-space matrices and other information.

The following applies to the SML formats (FileFormat = 2, 3, and 4):

- For conservative systems where the outputs are equal to the inputs ( `Outputs` is left blank):
- The labels for the inputs ( `InputLabels` ) are required.
- The `Inputs` must use the array parameter option so that the input degrees of freedom (DOFs) are known.
- For non-conservative systems where the outputs are not equal to the inputs:
- The labels for the outputs ( `OutputLabels` ) are required.
- The file formats with references ( `FileFormat` = 3 and 4) do not apply.
- Velocity and acceleration results are not included in the state-space matrices calculation (VelAccKey = OFF)
- File format with common reference (FileFormat = 3) does not apply if the inputs are based on DOFs of a different nature. All input DOFs must be either all rotational or all translational and not a mix of the two.
- A graphics file ( `Jobname_SPM.PNG` ) is generated. It contains an element plot of the model.

For more details about the reduction method and the generation of the state-space matrices, see [Reduced-Order Modeling for State-Space Matrices Export](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thystatespacemat.html#eq02c48d71-fb56-4172-a237-77dcfe5729e7)

For examples of the command usage, see [State-Space Matrices Export](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advstatspacmat.html)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPMWRITE.html
