<!-- cursor-review-bots:managed -->

# Bugbot rules

These rules apply to the **entire repository**. Review every PR path. There is no subdirectory opt-out.

## Blocking findings

- Commits `.env`, PEM keys, raw tokens, webhook secrets, or private keys.
- Weakens authentication, authorization, or signature verification (Slack, GitHub, Stripe, or similar).
- Uses a non-constant-time compare for secrets or signatures.
- Turns a local-only / debug login on in production.
- Adds a network listener, webhook, or MCP/API write path without auth.
- Changes infrastructure or deploy config in a way that drops a live production host.

## Non-blocking findings

- A TODO/FIXME with no tracked issue reference.
- Backend or API changes with no accompanying test.

## Do not flag

- Generated agent stubs rewritten by a framework (`AGENTS.md`, `CLAUDE.md`).
