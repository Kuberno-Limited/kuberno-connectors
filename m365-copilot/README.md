# Kube for Microsoft 365 Copilot

Connect **Microsoft 365 Copilot** to your **Kube** corporate-registry and entity-management platform, published by [Kuberno](https://kuberno.com). This is a declarative agent that lets Copilot search and read your organisation's entities, officers, and their appointments — all scoped to what your Kube user is permitted to see.

## What it does

A **read-only** agent over your Kube data, powered by the Kube remote MCP server:

- **Search** — entities and officers, with filters (registrar / country / type / jurisdiction, appointment type, nationality, and more).
- **Entities** — details, appointments, compliance dates, and roles for a given entity.
- **Officers** — details, appointments, and roles for a given officer.
- **Field catalogues** — so Copilot uses your instance's own field labels.

Every result respects Kube's per-user access permissions and field-level redaction — the agent never returns anything you couldn't already see in Kube. It is strictly read-only: it cannot create, change, or delete data.

## Requirements

- A **Kube account** with access to the relevant records.
- A **Microsoft 365 Copilot** licence, and permission from your Microsoft 365 admin to use custom agents.
- The agent authenticates via **OAuth 2.1** — you sign in with your Kube account and authorise access; Copilot then acts within your existing permissions.

## Install

Download **`kube-copilot.zip`** from the latest release:

<https://github.com/Kuberno-Limited/kuberno-connectors/releases/latest/download/kube-copilot.zip>

Then either sideload it (Microsoft 365 Copilot → **Agents** → **Add agents** → **Upload custom agent**) or hand the package to your Microsoft 365 admin to publish to your organisation. Enable it and complete the Kube sign-in when prompted.

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

MIT © 2026 Kuberno Limited — see [LICENSE](./LICENSE).
