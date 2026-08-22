---
apdl: "SHPP"
method: shpp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.shpp
generated: 2026-08-22
tags: [mapdl-command]
---

# SHPP

PyMAPDL: `mapdl.shpp(lab='', value1='', value2='', **kwargs)`

Controls element shape checking.

## Parameters

**lab**

Shape-checking option. (When `Lab` = WARN, STATUS, SUMMARY, or DEFAULT, the remaining arguments are ignored.)

- `ON` - Activates element shape-checking. New elements, regardless of how they are created, are tested against existing warning and error limits. (The existing limits may be the default limits, or previously modified limits.) Elements that violate error limits produce error messages and either

  \(a\) cause a meshing failure, or (b) for element creation or storage other than [[amesh|AMESH]] or [[vmesh|VMESH]], are not stored. Elements that violate warning limits produce warning messages. If shape-checking was previously turned off ( **SHPP**,OFF) and you turn it on, existing elements are marked as untested; use the [[check|CHECK]] command to retest them. With this option, you may also specify a value for `VALUE1` to turn individual shape tests on. If you do not specify a value for `VALUE1`, all shape tests are turned on.

- `WARN` - Activates element shape-checking; however, in contrast to **SHPP**,ON, elements that violate error limits do not cause either a meshing or element storage failure. Instead, they produce warning messages to notify you that error limits have been violated. This option does not alter current shape parameter limits. Since the default shape parameter error limits are set to allow almost any usable element, the elements this option allows, which would otherwise be forbidden, are likely to be very poorly shaped.

- `OFF` - Deactivates element shape-checking. This setting does not alter current shape parameter limits. Use of this option is risky, since poorly shaped elements can lead to analysis results that are less accurate than would otherwise be expected for a given mesh density. With this option, you may also specify a value for `VALUE1` to turn individual shape tests off. If you do not specify a value for `VALUE1`, all element shape tests are turned off.

- `SILENT` - Determines whether element shape-checking runs in silent mode. In silent mode, Mechanical APDL checks elements without issuing warnings, with the exception of the generic warnings that it issues at solution. With this option, you must also specify a value for `VALUE1` (During the execution of certain commands, Mechanical APDL automatically runs element shape-checking in silent mode, then internally summarizes the shape test results for all of the new or modified elements. Mechanical APDL does this when it executes any of the following commands: [[agen|AGEN]], [[amesh|AMESH]], [[arefine|AREFINE]], [[arsym|ARSYM]], [[atran|ATRAN]], [[cdread|CDREAD]], [[egen|EGEN]], [[engen|ENGEN]], [[ensym|ENSYM]], [[eread|EREAD]], [[erefine|EREFINE]], [[esym|ESYM]], [[et|ET]], [[fvmesh|FVMESH]], [[krefine|KREFINE]], [[lrefine|LREFINE]], [[nrefine|NREFINE]], [[timp|TIMP]], [[vext|VEXT]], [[vgen|VGEN]], [[vimp|VIMP]], [[vmesh|VMESH]], [[voffst|VOFFST]], [[vrotat|VROTAT]], [[vsweep|VSWEEP]], [[vsymm|VSYMM]], and [[vtran|VTRAN]].)

- `STATUS` - Lists the shape parameter limits currently in effect, along with status information about element shape-checking (for example, whether any individual shape tests are off, whether any of the shape parameter limits have been modified, and so on).

- `SUMMARY` - Lists a summary of element shape test results for all selected elements.

- `DEFAULT` - Resets element shape parameter limits to their default values. Also, if any individual tests were turned off, turns them back on. (The **SHPP**,DEFAULT command may be useful if any parameter limits were previously altered by using the MODIFY option.)

- `OBJECT` - Determines whether element shape test results data is stored in memory. When this option is turned on, an "object" is created for storing test results in memory. When this option is turned off, no object is created and no data is stored; thus, any operation that requires shape parameters for an existing element (such as use of the [[check|CHECK]] command) causes the shape parameters to be recomputed. (Note the distinction between storing the data in memory and storing it in the database; regardless of whether this option is turned on or off, no element shape test results data will be stored in the database. The element shape parameter object is deleted automatically before any solution.) This setting is independent of shape-checking status, with one exception-if shape- checking is turned off ( **SHPP**,OFF), the object is not created. Keep in mind that recomputing shape parameters is more computationally expensive than retrieving them from the object. With this option, you must also specify a value for the `VALUE1` argument; the `VALUE2` argument is ignored.

- `LSTET` - Determines, for Jacobian ratio tests, whether sampling is done at integration points or at corner nodes. When this option is turned on, sampling is done at integration points, and the default limits for h-element Jacobian ratios are a warning tolerance of 10 and an error tolerance of

  40\. When this option is turned off, sampling is done at corner nodes, and the corresponding default limits are a warning tolerance of 30 and an error tolerance of 1000. Sampling at the integration points (option on) results in a lower Jacobian ratio, but that ratio is also subjected to a more restrictive error limit. Some elements that have passed the integration point sampling criterion, have failed the corner mode sampling criterion. Because of this, use integration point sampling only for simple linear analyses. For other types of analyses (e.g., nonlinear, electromagnetic), use sampling at corner nodes, which is the more conservative approach. With this option, you must also specify a value for the `VALUE1` argument; the `VALUE2` argument is ignored.

- `MODIFY` - Indicates that you want to respecify a shape parameter limit. With this option, you must also specify values for the `VALUE1` and `VALUE2` arguments.

- `FLAT` - Determines the warning and error limits used to test elements that may exhibit nonzero/nonconstant Z coordinates. With this option, you must also specify values for the `VALUE1` and/or `VALUE2` arguments.

**value1**: Valid for the ON, OFF, SILENT, OBJECT, LSTET, MODIFY, and FLAT options only. When `Lab` = ON or OFF, use `VALUE1` to individually control (that is, turn off or turn on) specific element shape tests. Thus, `VALUE1` can be ASPECT (aspect ratio tests), PARAL (deviation from parallelism of opposite edges tests), MAXANG (maximum corner angle tests), JACRAT (Jacobian ratio tests), WARP (warping factor tests), or ALL (all tests). When `Lab` = SILENT, `VALUE1` can be ON (to turn silent mode on) or OFF (to turn silent mode off). When `Lab` = OBJECT, `VALUE1` can be either 1, YES, or ON to turn on storage of element shape test data (the default); or it can be 0, NO, or OFF to turn off storage of element shape test data (delete the data and recompute as necessary). When `Lab` = LSTET, `VALUE1` can be either 1, YES, or ON to choose Jacobian sampling at integration points; or it can be 0, NO, or OFF to choose Jacobian sampling at nodes (the default). When `Lab` = MODIFY, `VALUE1` is the numeric location (within the shape parameter limit array) of the shape parameter limit to be modified. Locations are identified in the element shape-checking status listing ( **SHPP**,STATUS). For more information, see the examples in the **Notes** section. When `Lab` = FLAT, `VALUE1` is the warning limit for XY element constant Z sets performed at [[check|CHECK]] or [[solve|SOLVE]]. The default is 1.0e-8.

**value2**: Valid for the MODIFY and FLAT options only. When `Lab` = MODIFY, specifies the new limit for the shape parameter that is in the location indicated by the `VALUE1` argument. See the examples in the **Notes** section. When `Lab` = FLAT, `VALUE2` is the error limit. The default is 1.0e-2.

## Notes

The following examples illustrate how to use the **SHPP**,MODIFY, `VALUE1`, `VALUE2` command to respecify shape parameter limits. Assume that you issued the **SHPP**,STATUS command, and you received the output below:

``` apdl
ASPECT RATIO (EXCEPT EMAG)

   QUAD OR TRIANGLE ELEMENT OR FACE
        WARNING TOLERANCE ( 1) =   20.00000
        ERROR TOLERANCE   ( 2) =  1000000.
                   .
                   .
                   .
MAXIMUM CORNER ANGLE IN DEGREES (EXCEPT OR EMAG)
   TRIANGLE ELEMENT OR FACE
        WARNING TOLERANCE (15) =   165.0000
        ERROR TOLERANCE   (16) =   179.9000
```

Notice that in the sample output, the warning tolerance for aspect ratios is set to 20. Now assume that you want to "loosen" this shape parameter limit so that it is less restrictive. To allow elements with aspect ratios of up to 500 without causing warning messages, you would issue this command:

**SHPP**,MODIFY,1,500

Also notice that each shape parameter's numeric location within the shape parameter limit array appears in the sample output within parentheses. For example, the numeric location of the aspect ratio shape parameter (for warning tolerance) is 1, which is why "1" is specified for the `VALUE1` argument in the example command above.

Now notice that the sample output indicates that any triangle element with an internal angle that is greater than 179.9 degrees will produce an error message. Suppose that you want to "tighten" this shape parameter limit, so that it is more restrictive. To cause any triangle or tetrahedron with an internal angle greater than 170 degrees to produce an error message, you would issue this command:

**SHPP**,MODIFY,16,170

The existence of badly shaped elements in a model may lead to certain computational errors that can cause your system to terminate during solution. Therefore, you run the risk of a system abort during solution any time that you disable element shape-checking entirely, run shape-checking in warning- only mode, disable individual shape-checks, or loosen shape-parameter limits.

Changing any shape parameter limit marks all existing elements as untested; use the [[check|CHECK]] command to retest them.

For more information about element shape-checking, see [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_8.html).

This command is also valid for [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SHPP.html
