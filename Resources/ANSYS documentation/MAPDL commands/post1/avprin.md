---
apdl: "AVPRIN"
method: avprin
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.controls.Controls.avprin
generated: 2026-08-22
tags: [mapdl-command]
---

# AVPRIN

PyMAPDL: `mapdl.avprin(key='', effnu='', **kwargs)`

Specifies how principal and vector sums are to be calculated.

**Command default:**

Average components at common node before principal or vector sum calculation except for the von Mises equivalent strain (EQV), see below.

## Parameters

**key**

Averaging key:

- `0` - Average the component values from the elements at a common node, then calculate the principal or vector sum from the averaged components (default).
- `1` - Calculate the principal or vector sum values on a per element basis, then average these values from the elements at a common node.

**effnu**: Effective Poisson's ratio used for computing the von Mises equivalent strain (EQV). This command option is intended for use with line elements or in load case operations ( [[lcoper|LCOPER]] ); the program automatically selects the most appropriate effective Poisson's ratio, as discussed below.

## Notes

Selects the method of combining components for certain derived nodal results when two or more elements connect to a common node. The methods apply to the calculations of derived nodal principal stresses, principal strains, and vector sums for selects, sorts, and output ( [[nsel|NSEL]], [[nsort|NSORT]], [[prnsol|PRNSOL]], [[plnsol|PLNSOL]], etc.). The calculation of these nodal results excludes beam and pipe elements.

This command also defines the effective Poisson's ratio ( `EFFNU` ) used for equivalent strain calculations. If you use `EFFNU`, the default effective Poisson's ratios shown below will be overridden for all elements by the `EFFNU` value. To return to the default settings, issue the [[reset|RESET]] command. The default value for `EFFNU` is:

- Poisson's ratio as defined on the [[mp|MP]] commands for EPEL and EPTH
- 0.5 for EPPL and EPCR
- 0.5 if the referenced material is hyperelastic
- 0.0 for line elements (includes beam, link, and pipe elements, as well as discrete elements), [cyclic symmetry analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/cycsym_example.html), mode superposition analyses (with `MSUPkey` = YES on the [[mxpand|MXPAND]] command), and load case operations ( [[lcoper|LCOPER]] ).
- For multistage analysis, a value of `EFFNU` must always be specified.

If `EFFNU` is specified, the calculation of von Mises equivalent strain (EQV) is performed according to the `KEY` setting. However, if `EFFNU` is not specified, or if the **AVPRIN** command is not issued, the von Mises equivalent strain is calculated using the average of the equivalent strains from the elements at a common node (behavior of `KEY` =1) irrespective of the value of the averaging KEY.

For a random vibration (PSD) analysis (for more details, see [Review the Results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR6_8.html#strcovtlm61199)

- Issuing either **AVPRIN**,0 or **AVPRIN**,1 calculates the principal stresses using the appropriate averaging method. They are then used to determine SEQV. The output will have non-zero values for the principal stresses.
- If **AVPRIN** is not issued, the Segalman-Fulcher method is used to calculate SEQV. This method does not calculate principal stresses, but directly calculates SEQV from the component stresses; therefore, the output will have zero values for the principal stresses.

This command is also valid in POST26, where applicable.

See [Combined Stresses and Strains](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_str4.html#strucfailure)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AVPRIN.html
