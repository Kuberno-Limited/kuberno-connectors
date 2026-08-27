# Kube

Connect Claude to your **Kube** corporate-registry and entity-management platform, published by [Kuberno](https://kuberno.com). This plugin adds Kube's remote MCP connector to Claude Code / Cowork, letting Claude search and read your organisation's entities, officers, and their appointments — all scoped to what your Kube user is permitted to see.

## What it does

A set of **read-only** tools over your Kube data:

- **Search** — `search_parties` (entities + officers together), `search_entities` (filters include registrar / country / jurisdiction / entity type / classification / status / business unit), `search_officers` (filters include appointed entity / registrar / country / appointment type / directorship type / nationality).
- **Entities** — `get_entity`, `get_entity_appointments`, `get_entity_dates` (compliance dates), `get_entity_roles` (service roles such as auditor), `get_entity_contacts`, `get_entity_addresses`, `get_entity_meetings`, `get_entity_registrations`, `get_entity_activities`, `get_entity_alternates` (appointments held by an alternate), `get_entity_udfs` (your own user defined fields).
- **Officers** — `get_officer`, `get_officer_appointments`, `get_officer_roles` (service roles), `get_officer_alternates` (appointments held as an alternate), `get_officer_external_appointments` (appointments at companies outside Kube), `get_officer_committees`, `get_officer_contacts`, `get_officer_addresses`, `get_officer_udfs` (your own user defined fields).
- **My activities** — `get_my_activities`: the signed-in user's own workload — theirs and their teams' — across every entity they can see. Contrast `get_entity_activities`, which covers one named entity's activities whoever owns them.
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
