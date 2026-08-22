# Handover: ANSYS documentation conversion

For a chat dedicated to one job: turn the downloaded PyMAPDL command reference from HTML into markdown notes inside the vault, so that John's notes can link a method name straight to its documentation. Written 2026-08-22 evening by the understanding phase chat. John asked for this himself and will be grateful for it done well.

## Why

John's own words note `Ansys\Starter notes\5 - Model definition.md` ends with a "Table of methods" (Method, APDL, Does). He wants the Does column to become a link to the command's documentation, held locally in the vault as markdown, not a web link. The same table will grow in notes 6 to 8 as meshing, flags, loads and postprocessing get their own words treatment. Every method that appears there needs a page to land on.

## Inputs, all on disk

- The downloaded PyMAPDL 0.74.1 HTML docs: `D:\Pyansys projects\docs\pymapdl-0.74.1\` (gitignored). A second copy sits at `D:\Projects\Resources\pymapdl-0.74.1-docs\` (also gitignored). Same content.
- The command reference lives under `mapdl_commands\`: 1566 HTML pages, grouped by processor (`prep7` 527, `solution` 362, `post1` 217, `post26` 69, `database` 71, `session` 46, plus `apdl`, `aux*`, `graphics`, `map`, `misc`). Each group has category pages (`prep7\areas.html`, `prep7\primitives.html`) and the per command pages under `_autosummary\`, for example `mapdl_commands\prep7\_autosummary\ansys.mapdl.core._commands.prep7.primitives.Primitives.rectng.html`.
- The `_sources\*.rst.txt` files are autosummary stubs only, they carry no command text. The content is in the HTML, which Sphinx built from the PyMAPDL docstrings.
- The same docstrings are installed: `C:\Users\John\miniforge3\envs\pyansys\Lib\site-packages\ansys\mapdl\core\_commands\`. `Mapdl.rectng.__doc__` is the numpydoc source the HTML page was rendered from.
- pandoc 3.9.0.2 is on the machine at `C:\Users\John\AppData\Local\Pandoc\pandoc`. Tested: `pandoc -f html -t gfm --wrap=none page.html` converts, but the raw output carries the site chrome (breadcrumbs, search box, sidebar, `<span class="pre">` signature markup). The article body has to be isolated first.
- Python in the `pyansys` env has no `markdownify` or `beautifulsoup4` installed. Check before assuming. The `jupyter` env is for the frontend, do not install into it.

## What a converted page should look like

One markdown file per command. Contents, in this order: the APDL command name as the title, the PyMAPDL signature, the one line summary, the parameters with their descriptions, the Notes section, and the link to the Ansys online help page that the HTML carries (`ansyshelp.ansys.com/...Hlp_C_RECTNG.html`), kept as a plain URL line at the bottom. Drop the breadcrumbs, the search box, the "Link to this heading" anchors, the Python type cross references (`str` linking to docs.python.org), and the sidebar.

Test page: RECTNG. Expected body, roughly:

```
# RECTNG

PyMAPDL: `mapdl.rectng(x1='', x2='', y1='', y2='', **kwargs)`

Creates a rectangular area anywhere on the working plane.

## Parameters

x1, x2: working plane X coordinates of the rectangle.
y1, y2: working plane Y coordinates of the rectangle.

## Notes

The area will be defined with four keypoints and four lines. See the BLC4 and BLC5 commands for alternate ways to create rectangles.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RECTNG.html
```

## Where the notes go, and how they are named

Proposed, to confirm with John at the start: `D:\Projects\Resources\ANSYS documentation\MAPDL commands\<group>\<method>.md`, with `<group>` the processor folder from the docs (`prep7`, `solution`, ...) and `<method>` the PyMAPDL method name in lower case (`rectng.md`, `aglue.md`, `clear.md`). Reasons: the method name is what John types in code and reads in the table, it is unique, and it has no slash (the APDL form `/CLEAR` cannot be a filename). The note title inside carries the APDL form. Obsidian resolves `[[rectng]]` from anywhere in the vault, so the table in note 5 links by `[[rectng|RECTNG]]` without a path.

Two name collisions to handle: a few methods exist in more than one processor group with different meanings (check for duplicates across groups before writing, and suffix the group on the rarer one if found). And Obsidian treats note names case insensitively, so `file.md` and `FILE.md` would collide, which the lower case rule avoids.

## Mechanism, recommended

Generate from the installed docstrings rather than scrape the HTML. The docstrings are the source the HTML was built from, they are numpydoc rst, and `pandoc -f rst -t gfm` handles them cleanly with none of the chrome stripping. The HTML is then the check, not the input. Sketch:

1. Walk `ansys.mapdl.core._commands` with `inspect`, collect every public method, its qualified class (which gives the group), its signature, and its docstring.
2. Pass the docstring through pandoc rst to gfm, or through a small numpydoc parser if pandoc mangles the parameter lists. Test on RECTNG, AGLUE, ET, MP, CLEAR, ASEL, CM, SF, SFE, D, F, SOLVE, NSOL first. Those thirteen cover the table in note 5 and the ones notes 6 to 8 will need.
3. Write the files. Log a count per group and the total. 1566 is the target, the HTML page count.
4. Spot check ten pages against their HTML by eye, including at least one with a table in the notes section and one with a long parameter list.

If John prefers the HTML route after all, isolate `<article class="bd-article">` (or `div#main-content`) before pandoc, and strip `span.pre`, `a.headerlink`, and the breadcrumb list.

## Rules that apply in this vault

- Read `D:\Projects\CLAUDE.md` first. No AI lexicon, no dash characters of any kind in vault notes, semicolons near zero, engineering vocabulary, no hard wraps. Generated pages are vault notes and follow the same rules. Pandoc output will contain en dashes and double hyphens from the source text, replace them (a comma, a colon, "to" for ranges) in a post pass.
- The vault auto commits through obsidian-git. Never commit or push from the session. Writing 1566 files will produce one large auto commit, which is fine, but say so to John before the write so he is not surprised.
- Notes under `Ansys\` are John's own words notes, do not write into them. This job writes only under `Resources\ANSYS documentation\`. The one edit outside that folder is turning the Does column of the table in `Ansys\Starter notes\5 - Model definition.md` into links, and that is done only after John approves the link style in chat.
- Show drafts in chat before writing into any of John's notes. For the generated reference pages that rule is satisfied by showing him the RECTNG page and the folder layout first, then generating.
- Text placed between tool calls in one turn is not shown to John in full in this interface. Put anything he must read at the end of the turn.

## Done when

- The folder exists with one page per command, count reported against 1566.
- RECTNG, AGLUE, ET, KEYOPT, MP, CLEAR, PREP7, ASEL, LSEL, CM, ALLSEL open in Obsidian and read cleanly.
- The table in note 5 links its APDL column to the pages, in the form John approved.
- A short record of the mechanism and any pages that failed conversion is left in `D:\Projects\LLM\` as a dated file, so the job can be rerun when PyMAPDL is upgraded.

## Related

Planner for the understanding phase: `Ansys\Starter notes\0 - Planner.md`. The table this serves: `Ansys\Starter notes\5 - Model definition.md`, section "Table of methods".
