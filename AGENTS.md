# AGENTS.md — (far-apps repo)

> An app is not a vibe.

This file is the contract. Every commit gate checks against it.
Every app references it. Every test (A1..A5) reads it.

If you change the schema, update AGENTS.md first. The repo is
downstream of this file.

## What this repo is

Apps + services + shop companion. Voice pipeline tools, vocab app,
claim-based indexers.

## Anti-patterns (refused at every layer)

- Silently generating output from an unsigned memo (companion refuses).
- Vendor-locked APIs without PD source check (gate refuses).
- "Make it punchy" without named axes (voice gate refuses).
- One-shot generation without Interrogative Planning (companion refuses).

## Surface

```python
shop.create_project(name)
shop.add_slice(text, voice="lean")
shop.lock(slice_id)
companion.query(text)
indexer.scan_repos(query)
```

## Gate

`commit_asset` defaults to `{gate}`. The gate checks:

1. `app_id` is set.
2. `app_id == sha256(canonical(axes))`.
3. Source-discipline: every data source is named.
4. Vendor-lock check: PD sources preferred.
5. Refuses to ship an app from a vibe prompt without going through
   Interrogative Planning (`vault/20-writing/methods/03-...`).

A naked app (no `app_id`) is refused with reason `no_app`.

## Tests

| # | Test | What it checks |
|---|---|---|
| A1 | repro id | App with same axes → same id; different axes → different id. |
| A2 | PD-source-only | App with PD sources only passes gate. |
| A3 | vendor-locked refused | App with non-PD sources refused. |
| A4 | no Interrogative Planning refused | App without planning log refused. |
| A5 | shop companion refuses unsigned | Shop companion refuses to generate chapter from unsigned memo. |

## Sister files

- `README.md` — the contract overview.
- `vault/50-apps/README.md` — the canonical meta-plan for this folder.

## Sister repos

- `the-far-queen/simself` — constitutional kernel.
- `the-far-queen/fieldcore` — math substrate.
- `the-far-queen/far-art` — UI kit framework.

## License

MIT. Free for all agents, human and non-human.
