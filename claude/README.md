# Kube

Connect Claude to your **Kube** corporate-registry and entity-management platform, published by [Kuberno](https://kuberno.com). This plugin adds Kube's remote MCP connector to Claude Code / Cowork, letting Claude search and read your organisation's entities, officers, and their appointments — all scoped to what your Kube user is permitted to see.

## What it does

A set of **read-only** tools over your Kube data:

- **Search** — `search_parties` (entities + officers together), `search_entities` (with registrar / country / type / jurisdiction / SIC / business-unit filters), `search_officers` (with appointed-entity / registrar / appointment-type / nationality filters).
- **Entities** — `get_entity`, `get_entity_appointments`, `get_entity_dates` (compliance dates), `get_entity_roles`.
- **Officers** — `get_officer`, `get_officer_appointments`, `get_officer_roles`.
- **Field catalogues** — `list_entity_fields`, `list_officer_fields` (so Claude uses your instance's own field labels).

Every result respects Kube's per-user access permissions and field-level redaction — the connector never returns anything you couldn't already see in Kube. It is strictly read-only: it cannot create, change, or delete data.

## Requirements

- A **Kube account** with access to the relevant records.
- The connector authenticates via **OAuth 2.1** — you sign in with your Kube account and authorise access; Claude then acts within your existing permissions.

## Install (Claude Code)

```bash
claude plugin marketplace add Kuberno-Limited/kuberno-connectors
claude plugin install kube-by-kuberno@kuberno
```

Then enable it and complete the sign-in when prompted. (The plugin ships **disabled by default** because it connects to an external service — enable it explicitly.)

## Example prompts

- "Find the directors of Acme Ltd."
- "List our entities incorporated in Jersey."
- "What compliance dates are coming up for entity E|6FE4BF?"
- "Show every appointment and role Jane Smith holds across the group."

## Privacy

See our privacy policy: https://kuberno.com/legal-notices/

## Support

https://kuberno.com/contact/

## License

MIT © 2026 Kuberno Limited
