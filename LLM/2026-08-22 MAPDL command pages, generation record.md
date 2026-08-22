# MAPDL command pages: generation record

One markdown page per PyMAPDL command under `Resources\ANSYS documentation\MAPDL commands\`, generated 2026-08-22 from the docstrings installed with PyMAPDL 0.74.1 by `D:\Pyansys projects\LLM\gen_command_pages.py`. Handover that defined the job: [[2026-08-22 Handover, ANSYS documentation conversion]]. The table this serves: [[5 - Model definition|Model definition]], section Table of methods, whose APDL column now links to these pages.

## Decisions, in the order they were made

- Source is the installed docstrings (`ansys.mapdl.core._commands`), not the HTML download. The docstrings are the numpydoc rst the HTML was rendered from, and the HTML carries nothing the docstrings lack apart from one injected Returns line (see losses). The HTML is the check.
- Layout `MAPDL commands\<group>\<method>.md`, group being the subpackage name (`prep7`, `solution`, ...) plus `conn` and `inqfun` for the two top level modules. Method names are unique across the package (1458 methods, 1458 names, no case collision), so `[[rectng]]` resolves from anywhere in the vault without a path. John confirmed 2026-08-22.
- Page title is the APDL form (`/CLEAR`, `*DIM`, `RECTNG`), read from the docstring header line. It is the only reliable source: the Python names are mangled (`slashsolu`, `starset`, `dim`). 21 methods have no header line (20 `inq_func` helpers and `verify`) and fall back to the method name in upper case.
- Minimal frontmatter on every page: `apdl`, `method`, `group`, `source` (version stamp and dotted path), `generated`, `tags: [mapdl-command]`. Index pages per group (`<group> commands.md`) and a top index (`MAPDL commands.md`), tagged `mapdl-command-index`. Group indexes are not named `<group>.md` because nine group names are also command names (`prep7`, `post1`, `post26`, `aux2`, `aux3`, `aux12`, `aux15`, `graphics`, `map`).
- The APDL column of the Table of methods in note 5 carries the link, alias kept so the cell reads as before, pipe escaped inside the table: `[[clear\|/CLEAR]]`. Written 2026-08-22 on John's word, 13 cells, nothing else in the note touched.
- Cross references between commands become wikilinks with the APDL name as alias, `[[blc4|BLC4]]`. A command referring to itself is set bold. References to in page tables and footnotes become the heading text in italics, or the title text, or are dropped when bare with nothing to point at.
- Dash rule: the docstrings contain no em or en dash, only ` -- ` (264 places). Every double hyphen becomes the single hyphen the docstrings themselves use as label separator (`ALPD` - Mass matrix multiplier).
- PyMAPDL's own placeholder sentence for tables its converter dropped ("This command contains some tables and extra information which can be inspected in the original documentation pointed above", 116 places, seven of them fused with an anchor) is normalised to one marker line, `(table not available in the PyMAPDL source, see the Ansys help page)`.
- The "Argument Descriptions" block that 72 docstrings carry is cut as a duplicate of the Parameters section, except where more than a fifth of its sentences are absent from Parameters. Ten pages keep it as a subsection: the matrix commands DMAT, SMAT, VEC, INIT, AXPY, MERGE, REMOVE, *SORT, plus INQUIRE and MKDIR. In the matrix commands it holds the per Method meanings of Val1 to Val5.
- Nine commands whose PyMAPDL method is overridden by a wrapper (`run`, `aplot`, `eplot`, `kplot`, `lplot`, `nplot`, `vplot`, `mpread`, `geometry`) carry one line after the signature saying so, with `mapdl.run("RUN,...")` as the way to issue the APDL command. Detected at run time by comparing the `MapdlBase` docstring with the `_commands` one.

## Mechanism, in a paragraph

Six stages, one process, two pandoc calls. Collect: walk the package with `pkgutil` and `inspect`, keep public methods defined in each class. Parse: split the numpydoc sections in Python, so parameter names (94 of them end in an underscore, which rst reads as a reference) never reach pandoc. Pre pass on each rst fragment: normalise the table placeholders, strip anchor lines, fix apostrophes typed as double backticks (41, they unbalance the literal markup and an unbalanced literal swallows every following fragment in a batch), canonicalise heading underline characters per fragment (pandoc assigns levels by first appearance across the stream), wrap doctests in code blocks (62), replace figures with a marker (38). Pandoc rst to JSON in one call over all 8944 fragments, each preceded by a numbered section title sentinel underlined with `=`, a character no docstring uses. Fragments with an odd backtick count go through a standalone call. Transform the JSON AST in Python: wikilinks, the 134 `flat-table` directives rebuilt as pandoc tables with row span expansion and padding, boilerplate warnings dropped (99), dud equations replaced (201, the source has the literal text "equation not available"), dashes, code block classes, heading shift. Pandoc JSON to GFM in one call with `--eol=lf`, split on the sentinels, assemble each page, write UTF-8. Whole run 24 s.

## Counts from the run of 2026-08-22

- 1458 command pages: apdl 84, aux12 11, aux15 3, aux2 8, aux3 7, conn 6, database 64, graphics 93, inqfun 20, map 8, misc 1, post1 200, post26 60, prep7 518, session 41, solution 334. Plus 16 group indexes and the top index, 1475 files, 3.7 MB.
- Against the HTML download (1438 command pages): every HTML page has a markdown page, and 20 pages exist only from the docstrings, the 19 explicit dynamics `ed*` commands the HTML build dropped and `wrinqr`. The handover's 1566 was the HTML page count including the 128 category pages.
- Text coverage: the article text of every HTML page cut into 29392 chunks of 40 characters or more, 244 absent from the markdown (0.83 percent), all of them either the placeholder sentence replaced by the marker, the boilerplate warning, or the injected Returns line below.
- 6260 wikilinks, 2286 bold self references, 49 links to another page's Notes section, 1567 parameter entries merged with an identical neighbour (`x1`, `x2`, or `na1` to `na9`).

## What the pages do not carry

- Figures: 38, replaced by `(figure omitted: caption, see the Ansys help page)`. The image files are not in the docstrings.
- Equations: 201, the PyMAPDL source holds "equation not available" in their place.
- Tables the PyMAPDL converter dropped: 116 markers.
- A one line Returns entry ("Str object with the command console output") that the Sphinx build injects on 28 listing commands (`prsect`, `nlist`, `dlist`, ...). It is in the HTML, not in any runtime docstring.
- Malformed rst passed through as text on three pages: BF (`<sup>3</sup> *s`), CUTCONTROL (a literal `:ref:` inside bold), TB (`:sub:` inside a literal).
- 161 bare footnote references dropped with nothing to point at, and one table (GET, RCON item) with a row wider than its header.
- Obsidian renderings John was asked to check: an alias beginning with a star, `[[dim|*DIM]]`, and the `> [!WARNING]` callout on the `inqfun` pages.

## Rerun after a PyMAPDL upgrade

```
conda run -n pyansys python "D:\Pyansys projects\LLM\gen_command_pages.py" --prune --report "D:\Pyansys projects\scratch\gen_report.txt"
```

Pages are overwritten in place and the date in `generated` changes on all of them, so the obsidian-git diff is the whole folder. `--prune` deletes pages whose method no longer exists (without it they are listed). Add `--html <docs dir>` when a matching HTML download exists, to print the set difference. The report lists the conversion counts and any page failing the post write checks (dash characters, escaped wikilinks, raw HTML, sentinels, rst leftovers). `--only rectng,dim,psf` with `--out <scratch dir>` is the test mode. The group titles and descriptions in the top index are hardcoded in the script from the 0.74.1 docs index, adjust if a group is added.
