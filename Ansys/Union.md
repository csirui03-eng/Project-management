PyAnsys does not automatically detect and join coincident geometric edges — a command has to be explicitly called to glue them together: `AGLUE,ALL` (areas; `LGLUE`/`VGLUE` for lines/volumes). Until then, shapes drawn edge-to-edge hold *two* coincident lines, one each; meshed like that they get duplicate nodes and no physics crosses the seam — and every plot looks fine.

Tolerance of the glue's coincidence detection: set by `BTOL` (default 1e-5, relative to model scale; adjust via `mapdl.btol()`). But in well-coded geometry this doesn't matter — shared coordinates should come from the same variable, so both sides are bit-for-bit identical and coincidence is exact by construction. Reaching for `BTOL` usually means two coordinates that should be one variable aren't.

This is exactly the "Form Union" node at the end of a COMSOL geometry sequence — COMSOL just runs it for you by default, which is why edges feel auto-glued there. MAPDL makes you say it.

Because glue is a boolean, it renumbers entities: name things (`CM`) only after the glue, never before.
