# sagrada-specimen

A test repo with scripted git history for
[sagrada-linter](https://github.com/Cruxia-Labs/sagrada-linter). Every commit
is synthetic, with fixed dates. Nothing here measured anything real.

## Try it

```
git clone https://github.com/Cruxia-Labs/sagrada-specimen
cd sagrada-specimen
uvx sagrada-linter read .
```

No install, in a browser: paste `Cruxia-Labs/sagrada-specimen` into the
reader at [cruxia.dev](https://cruxia.dev/) (or
[cruxia.ai/graveyard](https://cruxia.ai/graveyard/)). Runs against the
GitHub API from your browser; check devtools.

## What's planted

| rule | history | status |
|---|---|---|
| `deploy-gate` | removed 2026-02-14, back via merge 2026-05-19, undeclared | WALKING |
| `tone` | removed 2026-03-02, back 2026-03-28, declared with `sagrada:allow` 2026-04-02 | RESTORED WITH INTENT / EXHUMED |
| `changelog` | removed 2026-03-20, restored 2026-07-30 with the marker *in the revival commit itself* | EXHUMED in the browser reading; `read` counts an inline-marker revival as a rewrite (its documented different-wording edge), so the CLI omits it |
| `license-header` | retired 2026-07-30, still gone | INTERRED |
| `api-version-pin` | retired 2026-07-30, still gone | INTERRED |
| `retry-limit` | removed 2026-07-30 by `sagrada-linter forget` — dated tombstone in `.sagrada/tombstones.jsonl`, signed receipt beside it | ENTOMBED |
| `secrets` | never touched | — |

Expected tallies, honestly stated (the two instruments read differently):

- CLI — `uvx sagrada-linter read .` → `1 walking · 1 restored with intent`
- browser reading → `1 WALKING · 2 EXHUMED · 2 INTERRED · 1 ENTOMBED`
  (the browser strips the marker comment before pairing, and reads the
  tombstone ledger; the CLI is the instrument of record)

## The gauntlet

The PR tab is part of the specimen. Pull requests that re-add a retracted
rule without declaring it are blocked by `sagrada-linter guard --check` in
CI, with the rule's kill history in the failure. A declared restoration
(`sagrada:allow` + reason) passes. Try it: open a PR that brings any locked
rule back.
