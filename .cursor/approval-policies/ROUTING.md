<!-- cursor-review-bots:managed -->

- product: app
  boundary: "**"
  policies:
    - APPROVAL_POLICY.md
- product: cursor-bots
  boundary: "{.cursor/**,APPROVAL_POLICY.md}"
  policies:
    - APPROVAL_POLICY.md
    - Changes to review-bot rules or approval policy require human review. Use the base-branch version when deciding this PR.
