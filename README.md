# translation-suite

A game-agnostic harness for running a fan translation of a tokenised game script as an unattended,
self-continuing loop of Claude Code agents: parallel translators, one reviewer that gates and merges,
a coordinator per wave that opens the next wave's session, a watchdog that never lets the chain die
silently, and a live board that lets any fresh session resume. Extracted from a completed PS1
project and generalised; the incidents behind each rule are in `docs/LESSONS.md`.

What it is **not**: a dumper, an inserter or a font hack. Those are per engine. `tools/README.md`
specifies the seven commands the suite needs from yours.

## Layout

| File | Role | Edited by |
|---|---|---|
| `CLAUDE.md` | the process contract — roles, waves, gates, board, stop rules | nobody, per project |
| `PROJECT.md` | every project-specific value, referenced by section number | the human, once; the reviewer adds CHECK blind spots |
| `HANDOFF.md` | the live board | coordinator and reviewer |
| `translation_prompt.md` | how to translate under the budget | the human, from the first unit |
| `glossary.md` | fixed terms, one row each, read in full before every unit | the reviewer |
| `rulings.md` | the reasoning behind the terms, grepped on demand | the reviewer |
| `FLAGS.md` | open issues | the reviewer; collapsed by the coordinator |
| `pending/` | finished work that cannot ship | translators, via `park:` PRs |
| `tools/README.md` | the command contract the tools must meet | the human |
| `docs/LESSONS.md` · `docs/PROJECT.example.md` | why each rule exists · a filled project block | optional reading |
| `.claude/` | the `/translate` skill, the three agent roles, the permission allowlist | nobody, per project |
| `.github/pull_request_template.md` | the PR shape every translator fills | nobody, per project |

## Adopting it for a game

1. Copy everything into the game's repo root. Keep the file names: the agents refer to them.
2. Build the tools to `tools/README.md`'s contract. Put the pristine dumps under `dumps/`. Confirm
   CHECK passes on an empty `tl/` and **fails** on a planted violation of each kind; record those in
   `FLAGS.md` → CHECK positive controls.
3. Fill `PROJECT.md` until `grep -n '«FILL»' PROJECT.md` prints nothing. The runner refuses to start
   otherwise. `docs/PROJECT.example.md` shows a completed one.
4. Translate the **first unit by hand, or in one attended session**, measure the natural and
   disciplined ratios, and fill `PROJECT.md` §4's tiers and `translation_prompt.md` §0.2 and §5 from
   it. Do not copy another project's bands: they depend on bytes per target character.
5. Fill `translation_prompt.md`'s remaining `«FILL»`s: the tag table, the charset consequences, the
   worked examples.
6. Seed `glossary.md` §9 PROVISIONAL from the dumps if you already know names.
7. If `opus` is not the model you want, change the alias in `.claude/settings.json` and the four
   frontmatter blocks together. Answer `PROJECT.md` §9's environment questions honestly: without the
   claude-code-remote MCP the run is attended, and the files say so.
8. Commit to `main`, run `/translate` in a Claude Code session, and read `HANDOFF.md` whenever you
   want to know what is happening. Everything that needs you is under "Blocked — needs a human".

## What stays fixed

The integration branch is `main` and is not a setting. The three roles never collapse into one. A
wave is a session and opens the next. The watchdog is armed before every turn ends. Those four are
`CLAUDE.md`'s banner; everything else is a parameter in `PROJECT.md`.

## Status
<!-- The coordinator refreshes this table from STATUS at every wave close. -->
| Store | Done | Total |
|---|---|---|
| «store» | 0 | «n» |
