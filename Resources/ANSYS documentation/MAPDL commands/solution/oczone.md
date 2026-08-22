---
apdl: "OCZONE"
method: oczone
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.ocean.Ocean.oczone
generated: 2026-08-22
tags: [mapdl-command]
---

# OCZONE

PyMAPDL: `mapdl.oczone(zonetype='', zonename='', compnameint='', compnameext='', **kwargs)`

Specifies the type of ocean zone data to follow.

## Parameters

**zonetype**

The type of ocean zone data to be input following this command:

- `COMP` - Define by a component.
- `ZLOC` - Define by Z levels.
- `PIP` - Associate an internal pipe or pipes with an external pipe.

**zonename**: The ocean zone name. If no name is specified, the program assigns one.

**compnameint**

For `Zonetype` = COMP, the required name of a component.

For `Zonetype` = PIP, the required name of an internal pipe component.

**compnameext**: For `Zonetype` = PIP, the required name of an external pipe component.

## Notes

The **OCZONE** command specifies the type of ocean zone data to follow (component, Z-level, or internal pipes associated with an external pipe). An ocean zone is a local space where you can override global ocean-loading parameters.

Names specified for `ZoneName`, `CompNameInt`, and `CompNameExt` can consist of up to 32 alphanumeric characters. The name cannot contain punctuation, special characters, or spaces.

For `Zonetype` = COMP, the zone is defined by a component. Only the elements in the component are affected by the local parameters. A partial component can be defined as the zone via the Z input on the [[octable|OCTABLE]] command.

For `Zonetype` = ZLOC, the zone is defined by Z levels. Structural elements (such as `BEAM188`, `BEAM189`, `PIPE288`, `PIPE289`, and `LINK180` ) in the Z levels are included in the zone.

For `Zonetype` = PIP, the zone is prepared for a special configuration of pipes. It associates an internal pipe or pipes with an external pipe to remove the hydrodynamic effect on the internal pipe. Only hydrostatic pressure is applied on the internal pipe.

This command is also valid in PREP7.

(figure omitted: Ocean Zone Types (Specified via ZoneType), see the Ansys help page)

Issue this command before defining your ocean load data ( [[ocdata|OCDATA]] or [[octable|OCTABLE]] ). Define components before defining a component-type or a pipe-type zone ( **OCZONE**,COMP or **OCZONE**,PIP, respectively).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_OCZONE.html
