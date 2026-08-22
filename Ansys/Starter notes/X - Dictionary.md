# Dictionary

Started 2026-08-22 from the domain table discussion in [[5 - Model definition|Model definition]]. Concept note beside the numbered steps. Curly braces, `key: value` pairs, same type as `DW_GEOM`, `DW_MAT` and `DW_DOMAINS` in the model script.

## How to index one

Using `DW_DOMAINS` as the example, where each value is a tuple `(y band, x band, material, element type, mesh size)`.

By key:

- `DW_DOMAINS["W1_EDGE_A"]` returns the row. A missing key raises `KeyError`.
- `DW_DOMAINS.get("W1_EDGE_A")` same, but returns `None` for a missing key, or a default if given: `.get(name, None)`.
- `"W1_EDGE_A" in DW_DOMAINS` asks whether the key exists, true or false.

Then into the value:

- `DW_DOMAINS["W1_EDGE_A"][4]` is the mesh size, position 4 of the tuple, counting from 0.
- `DW_DOMAINS["W1_EDGE_A"][0][1]` is the top of the Y band: element 0 is the Y tuple, element 1 of that is `y2`.
- For nested dicts it is a key again: `DW_MAT["air"]["sonc"]`.

Iterating:

- `for name in DW_DOMAINS:` gives keys only.
- `for name, row in DW_DOMAINS.items():` gives key and value together. This is what the naming, attribute and mesh size loops use.
- `DW_DOMAINS.values()` gives values only, `DW_DOMAINS.keys()` keys only. `list(DW_DOMAINS)` is the list of names, derived rather than typed.

Unpacking inside the loop:

- `for name, ((ya, yb), (xa, xb), mat, typ, size) in DW_DOMAINS.items():` names every field at once.
- `*_` stands for "the rest, ignored", a bare `_` for one ignored field. Each of the three loops takes only the fields it needs this way.

One cost of positional tuples: `row[4]` means nothing without the header comment saying what position 4 is. If that bothers later, the value can be a small dict (`{"y": (y1, y2), "x": (...), "mat": 2, "type": 1, "size": ...}`) and the loops read `row["mat"]`. Same dict, more typing per row, readable without the header.
