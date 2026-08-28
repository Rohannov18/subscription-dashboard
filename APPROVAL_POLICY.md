<!-- cursor-review-bots:managed -->

# Approval policy

Applies to the whole repository. PR Routing & Approval must not auto-approve a pull request that touches any path in **Require human review**. Low-risk changes still need a human if Bugbot or Security Agents report unresolved findings.

## Require human review (never auto-approve)

- Auth, session, RBAC, and identity modules
- Secret storage, token minting, and webhook signature verification
- MCP / API write handlers and server actions that mutate data
- `.github/workflows/**`, `Dockerfile`, deploy manifests
- Database schema and migrations
- `.cursor/**` and this file

## Approval criteria (only when none of the above changed)

- Bugbot and Security Review reported no unresolved findings.
- The diff is docs, copy, tests, or isolated UI with no new network, auth, or secret handling.
- No new dependency with a copyleft license (GPL-2.0, GPL-3.0, AGPL-3.0).

## Reviewer routing

- Auth, tokens, and webhooks: request an owner or admin.
- Deploy: request whoever last changed the deploy workflow.
- Everything else: request reviewers from recent commit history on the touched paths.
