---
apdl: "OCTYPE"
method: octype
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.ocean.Ocean.octype
generated: 2026-08-22
tags: [mapdl-command]
---

# OCTYPE

PyMAPDL: `mapdl.octype(datatype='', name='', **kwargs)`

Specifies the type of ocean load data to follow.

## Parameters

**datatype**

The type of ocean data to be input following this command:

- `BASIC` - The basic ocean load, required for any ocean loading.
- `CURR` - An optional drift current.
- `WAVE` - An optional ocean wave state.

Specify basic, current, or wave input data via the [[ocdata|OCDATA]] and [[octable|OCTABLE]] commands. The example input fragment listed in the [Notes](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SECTYPE.html#SECTYPE.prodres) Notes section shows how to use the ocean load data types.

**name**: An eight-character name for the ocean load. An ocean name can consist of letters and numbers, but cannot contain punctuation, special characters, or spaces.

## Notes

The **OCTYPE** command specifies the type of ocean load data to follow (basic, current, or wave). Issue this command before defining your ocean load data ( [[ocdata|OCDATA]] and [[octable|OCTABLE]] ).

Ocean loading applies only to current-technology pipe ( `PIPE288` and `PIPE289` ), surface ( `SURF154` ), link ( `LINK180` ) and beam ( `BEAM188` and `BEAM189` ) elements.

An ocean current or wave is accessible repeatedly. For example, it is not necessary to input an identical current table again just because the drag coefficients of the basic input table have changed.

The following example shows how you can use the basic ( `DataType` = BASIC), current ( `DataType` = CURR), and wave ( `DataType` = WAVE) ocean data types within the context of a simple input file fragment:

``` apdl
Do=1.5                        ! outside diameter
th=0.1                        ! wall thickness
height=10                     ! wave height
CS=2                          ! surface current speed
Depth=100                     ! water depth
matwat=2                      ! material number id of the ocean
secpipe= 1                    ! section number of the pipe
!
sectype,secpipe,pipe,,pipetest
secdata,Do,th,16              ! 16 cells around circumference
!
octype,basic
ocdata,Depth,matwat,0,0,0,0   ! suppress added mass and buoyancy
octable,,,.5,.5,,2            ! CD =.5, CM = 2

octype,curr
octable,0.0,CS                ! input free surface current speed
octable,Depth,0.00            ! input ocean floor current speed of 0.0
!
octype,wave
ocdata,2                      ! request Stokes wave type
octable,height,8              ! wave period of 8 seconds

slist,all                     ! lists pipe section AND
!                                 mentions ocean loading
oclist,all                    ! lists details of ocean loading
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_OCTYPE.html
