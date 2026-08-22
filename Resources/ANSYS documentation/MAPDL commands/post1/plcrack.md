---
apdl: "PLCRACK"
method: plcrack
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1._special_purpose.SpecialPurpose.plcrack
generated: 2026-08-22
tags: [mapdl-command]
---

# PLCRACK

PyMAPDL: `mapdl.plcrack(loc='', num='', **kwargs)`

Displays cracking and crushing locations in [SOLID65](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_arch/Hlp_E_SOLID65.html#a5pNxq3a5mcm) elements.

## Parameters

**loc**

Location at which symbols are to be displayed:

- `0` - Plot symbols at integration points (default).
- `1` - Plot symbol at element centroids (averaged).

**num**

Crack to be displayed:

- `0` - Plot all cracks (default).
- `1` - Plot only the first crack.
- `2` - Plot only the second crack.
- `3` - Plot only the third crack.

## Notes

**PLCRACK** displays circles at locations of cracking or crushing in concrete elements. Cracking is shown with a circle outline in the plane of the crack, and crushing is shown with an octahedron outline. If the crack has opened and then closed, the circle outline will have an X through it. Each integration point can crack in up to three different planes. The first crack at an integration point is shown with a red circle outline, the second crack with a green outline, and the third crack with a blue outline.

Symbols shown at the element centroid ( `LOC` = 1) are based on the status of all of the element's integration points. If any integration point in the element has crushed, the crushed (octahedron) symbol is shown at the centroid. If any integration point has cracked or cracked and closed, the cracked symbol is shown at the element centroid. If at least five integration points have cracked and closed, the cracked and closed symbol is shown at the element centroid. Finally, if more than one integration point has cracked, the circle outline at the element centroid shows the average orientation of all cracked planes for that element.

Portions of this command are not supported by PowerGraphics ( [[graphics|/GRAPHICS]],POWER).

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLCRACK.html
