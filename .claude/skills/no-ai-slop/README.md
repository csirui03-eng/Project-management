# no-ai-slop -- the CLAUDE.md dependency

## Where the rules came from

The no-ai-slop material was originally packaged by Louis Rossmann, and it
shipped with a full project CLAUDE.md holding the numbered rule list
(rules 1 through 24). That CLAUDE.md did not travel into this plugin.
SKILL.md here carries the rules that have worked examples; the numbered
list itself stays a per-project file.

## Hard rule for every repo that uses this skill

Every repo whose CLAUDE.md points at no-ai-slop must carry the no AI
lexicon rule in that CLAUDE.md as a hard rule, stated in full:

    No AI lexicon: the furthermore/moreover/notwithstanding transitions,
    the delve/leverage/utilize/foster/underscore verbs, the
    robust/comprehensive/pivotal/seamless adjectives, the
    significantly/extremely intensifiers. No emdash character; double
    hyphens serve.

Without the CLAUDE.md line the ban only applies when the skill is
invoked; with it, the ban binds every session in the repo, prose task
or not.

## Copies of the ban already in this repo

Three agent files restate the lexicon ban independently of the skill:
`agents/cutter.md` (line 49), `agents/summariser.md` (line 49),
`agents/reflector.md` (line 40). The skill restates the word lists in
the SKILL.md self-check (steps 2 through 4) and in
`references/ai-writing-detection.md`. None of these follow a project
CLAUDE.md automatically; a change to the rule means updating each copy
by hand.
