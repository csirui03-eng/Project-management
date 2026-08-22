---
apdl: "CYCPHASE"
method: cycphase
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.cycphase
generated: 2026-08-22
tags: [mapdl-command]
---

# CYCPHASE

PyMAPDL: `mapdl.cycphase(type_='', option='', **kwargs)`

Provides tools for determining minimum and maximum possible result values from frequency couplets produced in a modal cyclic symmetry analysis.

**Command default:**

No defaults are available for the **CYCPHASE** command. You must specify an argument ( `TYPE` ) when issuing the command. Other values which may be necessary ( `OPTION` ) depend upon which `TYPE` argument you specify.

## Parameters

**type_**

The type of operation requested:

- `DISP` - Calculate the maximum and minimum possible displacement at each node in the original sector model. Store the values and the phase angle at which they occurred.
- `STRESS` - Calculate the maximum and minimum possible stresses at each node in the original sector model. Store the values and the phase angle at which they occurred.
- `STRAIN` - Calculate the maximum and minimum possible strains at each node in the original sector model. Store the values and the phase angle at which they occurred.
- `ALL` - Calculate the maximum and minimum possible displacement, stress and strain at each node in the original sector model. Store the values and the phase angle at which they occurred.
- `GET` - Places the value of a MAX or MIN item into the CYCVALUE parameter, the node for that value in the CYCNODE parameter, and the phase angle for the value in the CYCPHASE parameter.
- `PUT` - Put resulting sweep values for printing (via the [[prnsol|PRNSOL]] command ) or plotting (via the [[plnsol|PLNSOL]] command).
- `LIST` - List the current minimum/maximum displacement, stress and strain nodal values.
- `STAT` - Summarize the results of the last phase sweep.
- `CLEAR` - Clear phase-sweep information from the database.

**option**

If TYPE = DISP, STRAIN, STRESS or ALL, controls the sweep angle increment to use in the search:

- `Angle` - The sweep angle increment in degrees, greater than 0.1 and less than 10. The default is 1.

If TYPE = PUT, controls which values are placed onto the model:

- `MAX` - Put all existing nodal maximum values onto the model. This option is the default.
- `MIN` - Put all existing nodal minimum values onto the model.

If TYPE = GET, controls the values placed into cyclic parameters:

- `Item` - Specifies the type of values on which to operate:
  - U - Displacement
  - S - Stress
  - EPEL - Strain
- `Comp` - Specifies the specific component of displacement, stress or strain for which to get information:
  - X,Y,Z - Basic components
  - XY,YZ,XZ - Shear components
  - 1,2,3 - Principal values
  - EQV - Equivalent value
  - SUM - USUM
- `MxMn` - Specifies whether the requested value information is for the maximum or minimum value:
  - MAX - Maximum value.
  - MIN - Minimum value.

## Notes

When you [expand the results of a modal cyclic symmetry analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycpost.html#ans_cycsym_res_coord_sys) (via the [[cycexpand|/CYCEXPAND]] or [[expand|EXPAND]] command), the program combines the real and imaginary results for a given nodal diameter, assuming no phase shift between them; however, the modal response can occur at any phase shift.

**CYCPHASE** response results are valid only for the first cyclic sector. To obtain the response at any part of the expanded model, Ansys, Inc. recommends using [cyclic symmetry results expansion](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycpost.html#ans_cycsym_res_coord_sys) at the phase angle obtained via **CYCPHASE**.

The phase angles returned by **CYCPHASE** contain the minimum and maximum values for USUM, SEQV and other scalar principal stress and strain quantities; however, they do not always return the true minimum and maximum values for directional quantities like UX or SX unless the values fall in the first sector.

**CYCPHASE** does not consider midside node values when evaluating maximum and minimum values, which may affect display quantities but no others. (Typically, the program ignores midside node stresses and strains during postprocessing.)

Issuing **CYCPHASE**,PUT clears the result values for midside nodes on high order elements; therefore, this option sets element faceting ( [[efacet|/EFACET]] ) to 1. The command reports that midside nodal values are set to zero and indicates that element faceting is set to 1.

If the sweep values are available after issuing a **CYCPHASE**,PUT command, the [[prnsol|PRNSOL]] or [[plnsol|PLNSOL]] command will print or plot (respectively) the sweep values of structure displacement Ux, Uy, Uz, component stress/strain X, Y, Z, XY, YZ, ZX, principal stress/strain 1, 2, 3 and equivalent stress/strain EQV. The vector sum of displacement (USUM) and stress/strain intensity (SINT) are not valid phase-sweep results.

You can specify any coordinate system via the [[rsys|RSYS]] command for displaying or printing **CYCPHASE** results. However, after **CYCPHASE** results have been extracted, you cannot then transform them via the [[rsys|RSYS]] command. If you try to do so, the program issues a warning message.

The **CYCPHASE** command is valid in [[post1|/POST1]] and for cyclically symmetric models only.

To learn more about analyzing a cyclically symmetric structure, see the [Cyclic Symmetry Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/cycsym_example.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYCPHASE.html
