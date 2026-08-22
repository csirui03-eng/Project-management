---
apdl: "FSDELE"
method: fsdele
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1._fatigue.Fatigue.fsdele
generated: 2026-08-22
tags: [mapdl-command]
---

# FSDELE

PyMAPDL: `mapdl.fsdele(nloc='', nev='', nlod='', **kwargs)`

Deletes a stress condition for a fatigue location, event, and loading.

## Parameters

**nloc**: Delete stresses associated with location `NLOC`. Defaults to zero.

**nev**: Delete stresses associated with event `NEV`. Defaults to zero.

**nlod**: Delete stresses associated with loading `NLOD`. Defaults to zero.

## Notes

Deletes a stress condition stored for a particular fatigue location, event, and loading. Use FE command to delete all stresses for a particular event or FL command to delete all stresses for a particular location.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FSDELE.html
