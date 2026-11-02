# Kube for Microsoft 365 Copilot

Connect **Microsoft 365 Copilot** to your **Kube** corporate-registry and entity-management platform, published by [Kuberno](https://kuberno.com). This is a declarative agent that lets Copilot search and read your organisation's entities, officers, and their appointments — all scoped to what your Kube user is permitted to see.

## What it does

A **read-only** agent over your Kube data, powered by the Kube remote MCP server:

- **Search** — entities and officers, with filters (registrar / country / type / jurisdiction, appointed entity's registrar, appointment type, nationality, and more).
- **Entities** — details, appointments, compliance dates, roles, contacts, addresses, meetings, registrations, activities, alternates, and your own user defined fields.
- **Officers** — details, appointments, roles, alternates, external appointments at companies outside Kube, committees, contacts, addresses, and your own user defined fields.
- **Field catalogues** — so Copilot uses your instance's own field labels.

Every result respects Kube's per-user access permissions and field-level redaction — the agent never returns anything you couldn't already see in Kube. It is strictly read-only: it cannot create, change, or delete data.

## Requirements

- A **Kube account** with access to the relevant records.
- A **Microsoft 365 Copilot** licence, and permission from your Microsoft 365 admin to use custom agents.
- The agent authenticates via **OAuth 2.1** — you sign in with your Kube account and authorise access; Copilot then acts within your existing permissions.

## Install

Download **`kube-copilot.zip`** from the latest release:

<https://github.com/Kuberno-Limited/kuberno-connectors/releases/latest/download/kube-copilot.zip>

Uploading the agent is an admin task. Hand the package to an **AI Administrator** or **Global Administrator**, who deploys it from the [Microsoft 365 admin center](https://admin.cloud.microsoft/#/agents/all): click **Add Agent**, upload the zip file, and select the users who will be able to install the app.

Once it is deployed, Kube appears under **Built by your org** in Microsoft 365 Copilot. Complete the Kube sign-in the first time you open it.

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
