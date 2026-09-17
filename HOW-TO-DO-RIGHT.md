# How to do right — quick-reference (far-apps)

> For AI agents + humans working with Bobby Wolfson + Hermes on apps.

## The 5 rules

1. **Do not silently generate from an unsigned memo.** The shop
   companion refuses. Use Interrogative Planning
   (`vault/20-writing/methods/03-...`) to sign Gate 3 first.
2. **Do not vendor-lock.** Prefer public-domain sources (Wikimedia
   Commons, Project Gutenberg, Internet Archive, Standard Ebooks).
3. **Do not skip the voice gate.** Every app declares its voice axis.
   "Make it user-friendly" is not an axis. UX metrics + accessibility
   scores are.
4. **Do not conflate the substrate with the product.** SimSelf /
   FieldCore / far-* repos each have their own contract. Apps sit on
   top, not inside.
5. **Do not post without explicit consent.** Per Bobby's standing
   permission rule. Apps that publish (e.g. social media tools) need
   Bobby's explicit OAuth + API grant.

## The 5 anti-patterns (refused at every layer)

1. Silently generating output from an unsigned memo.
2. Vendor-locked APIs without PD source check.
3. "Make it punchy" / "make it user-friendly" without named axes.
4. One-shot generation without Interrogative Planning.
5. Posting to external services without Bobby's consent.

## The 5 tests (A1..A5)

- A1: same axes → same app_id.
- A2: PD-source-only app passes gate.
- A3: vendor-locked app refused.
- A4: app without planning log refused.
- A5: shop companion refuses unsigned memo.

## Sister files

- `README.md` — the contract overview.
- `AGENTS.md` — the schema contract.
- `vault/50-apps/README.md` — the canonical meta-plan.

## Sister repos

- [the-far-queen/simself](https://github.com/the-far-queen/simself) — kernel
- [the-far-queen/far-art](https://github.com/the-far-queen/far-art) — UI kit
- [the-far-queen/far-writing](https://github.com/the-far-queen/far-writing) — voice

## License

MIT. Free for all agents, human and non-human.
