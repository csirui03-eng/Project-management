---
apdl: "CORIOLIS"
method: coriolis
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.inertia.Inertia.coriolis
generated: 2026-08-22
tags: [mapdl-command]
---

# CORIOLIS

PyMAPDL: `mapdl.coriolis(option='', refframe='', rotdamp='', rotmass='', **kwargs)`

Applies the Coriolis effect to a rotating structure.

## Parameters

**option**

Flag to activate or deactivate the Coriolis effect:

`"ON"`, `"YES"`, or `True` - Activate. This value is the default.

`"OFF"`, `"NO"`, or `False` - Deactivate.

**refframe**

Flag to activate or deactivate a stationary reference frame.

`"ON"`, `"YES"`, or `True` - Activate.

`"OFF"`, `"NO"`, or `False` - Deactivate. This value is the default.

**rotdamp**

Flag to activate or deactivate rotating damping effect.

`"ON"`, `"YES"`, or `True` - Activate.

`"OFF"`, `"NO"`, or `False` - Deactivate. This value is the default.

**rotmass**

Flag to activate or deactivate rotor mass summary printout (only supported for `refframe='on'`).

`"ON"`, `"YES"`, or `True` - Activate.

`"OFF"`, `"NO"`, or `False` - Deactivate. This value is the default.

## Notes

The **CORIOLIS** command is used for linear analyses in either a rotating or a stationary reference frame, and performs differently according to the designated `RefFrame` value. The **CORIOLIS** command must be specified during the first step of the analysis. The rotational velocity must be defined using [[omega|OMEGA]] (when the whole model is rotating) or [[cmomega|CMOMEGA]] (component based rotation). Specific restrictions and elements apply to each case, as follows:

- [Rotating Reference Frame](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_ADVROTFR.html#) (, RefFrame = OFF) - The command applies the Coriolis effect in the following structural element types: `MASS21`, `SHELL181`, `PLANE182`, `PLANE183`, `SOLID185`, `SOLID186`, `SOLID187`, `BEAM188`, `BEAM189`, `SOLSH190`, `SHELL281`, `PIPE288` and `PIPE289`. It also applies this effect in the following coupled-field elements when structural degrees of freedom are present: `PLANE222`, `PLANE223`, `SOLID225`, `SOLID226`, and `SOLID227`.

  The rotating damping effect ( `RotDamp` = ON) is only supported by the `COMBI214` element when stationary.

  In a rotating reference frame, the Coriolis and [spin-softening](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/Hlp_G_ADVROTFR.html#) effects, as well as the centrifugal forces, contribute to the dynamics and are applied by default.

- [Stationary Reference Frame](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/Hlp_G_ROTGENDYNEQ.html#rotintrogendyneq2) (, RefFrame = ON) - The command activates the gyroscopic damping matrix in the following structural elements: `MASS21`, `BEAM188`, `SHELL181`, `BEAM189`, `SOLID185`, `SOLID186`, `SOLID187`, `SOLSH190`, `SOLID272`, `SOLID273`, `SHELL281`, `PIPE288`, `PIPE289`, and `MATRIX50`.

  The rotating structure is assumed to be axisymmetric about the axis of rotation.

  The rotating damping effect ( `RotDamp` = ON) is supported by the elements listed above that generate a gyroscopic damping matrix. It is also supported by some specific elements (see for a complete list).

  The rotor mass summary printout ( `RotMass` = ON) is only supported for some of the elements that generate a gyroscopic damping matrix: `MASS21`, `BEAM188`, `BEAM189`, `PIPE288`, and `PIPE289`. The EMAT file is required ( [[ematwrite|EMATWRITE]],YES).

To include Coriolis effects in a linear perturbation (prestressed) analysis, follow the procedure detailed in [Considerations for Rotating Structures](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strllinpertrotmach.html#str_rot_rotating)

In a nonlinear transient analysis in which the model is actually spinning ( [[antype|ANTYPE]],TRANS and [[nlgeom|NLGEOM]],ON) the **CORIOLIS** command must not be used as any spinning motion applied through either the [[ic|IC]] or [[d|D]] commands automatically includes nonlinear inertia terms such as the Coriolis effect.

To take into account variable bearings ( `COMBI214` elements with tabular user-defined characteristics), you must activate the Coriolis effect in a stationary reference frame. The gyroscopic effect coming from `COMBI214` mass characteristics is not supported.

For more information about using the **CORIOLIS** command, see [Rotating Structure Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advrrfexamples.html) in the [Advanced Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advoceanloading.html) and also in the [Rotordynamic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/rotdynappenda.html). For details about the Coriolis and gyroscopic effect element formulations, see the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html).

Elements with [layered section properties](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR11_2.html#atlQxq2f1mcm) do not support Coriolis effects (rotating and stationary reference frames).

This command is also valid in PREP7.

## Examples

Enable the coriolis effect with a stationary reference frame.

``` python
>>> mapdl.coriolis('ON', refframe='ON')
```

Alternatively, `coriolis` supports bool parameters.

``` python
>>> mapdl.coriolis(True, refframe=True)
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CORIOLIS.html
