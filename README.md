# sagrada-specimen

A test repo with scripted git history for
[sagrada-linter](https://pypi.org/project/sagrada-linter). Every commit is
synthetic, with fixed dates. Nothing here measured anything real.

## Try it

```
git clone https://github.com/Cruxia-Labs/sagrada-specimen
cd sagrada-specimen
uvx sagrada-linter read .
```

No install, in a browser: paste `Cruxia-Labs/sagrada-specimen` into the
reader at [cruxia.ai/graveyard](https://cruxia.ai/graveyard/). Runs against
the GitHub API from your browser; check devtools.

## What's planted

| rule | history | expected verdict |
|---|---|---|
| `deploy-gate` | removed 2026-02-14, back via merge 2026-05-19 | WALKING |
| `tone` | removed 2026-03-02, back 2026-03-28, declared with `sagrada:allow` 2026-04-02 | RESTORED WITH INTENT |
| `changelog` | removed 2026-03-20, never came back | resting |
| `secrets`, `retry-limit` | never touched | — |

Expected tally: `1 walking · 1 restored with intent`.

## The gauntlet

The PR tab is part of the specimen. Pull requests that re-add a retracted
rule without declaring it are blocked by `sagrada-linter guard --check` in
CI, with the rule's kill history in the failure. A declared restoration
(`sagrada:allow` + reason) passes. Try it: open a PR that brings any locked
rule back.
