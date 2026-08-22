---
apdl: "/SEG"
method: seg
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.seg
generated: 2026-08-22
tags: [mapdl-command]
---

# /SEG

PyMAPDL: `mapdl.seg(label='', aviname='', delay='', **kwargs)`

Allows graphics data to be stored in the local terminal memory.

## Parameters

**label**

Storage key:

- `SINGL` - Store subsequent display in a single segment (overwrites last storage).
- `MULTI` - Store subsequent displays in unique segments ( [[anim|ANIM]] ).
- `DELET` - Delete all currently stored segments.
- `OFF` - Stop storing display data in segments.
- `STAT` - Display segment status.
- `PC` - This option only applies to PC versions of Mechanical APDL and only when animating via the AVI movie player ( [[device|/DEVICE]],ANIM,2). The command appends frames to the `File.AVI`, so that the animation goes in both directions (that is, forward-backward-forward). You must have a current animation file to use this option.

**aviname**: Name of the animation file that will be created when each frame is saved. The `.AVI` extension is applied automatically. Defaults to `Jobname.AVI` if no filename is specified.

**delay**: Delay factor between each frame, in seconds. Defaults to 0.015 seconds if no value is specified.

## Notes

Allows graphics data to be stored in the terminal local memory (device-dependent). Storage occurs concurrently with the display.

Although the information from your graphics window is stored as an individual segment, you cannot plot directly ( [[gplot|GPLOT]] ) from the segment memory.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SEG.html
