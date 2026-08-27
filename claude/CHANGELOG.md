# Changelog

## 1.2.0
- Refresh the Search line's filter description in the README: `search_entities` and `search_officers` now have far more filters than the six and four the line named, so it now names representative filters from each rather than an exhaustive list that goes stale every time the server gains one more. The connector reads tool schemas live, so this is a docs-only fix — no functional change.
- Add `get_my_activities` to the README under a new **My activities** grouping — it was missing entirely. It covers the signed-in user's own workload, theirs and their teams', across every entity they can see, distinct from `get_entity_activities`'s one named entity for whoever owns it.

## 1.1.0
- Document the full toolset in the README: 11 entity tools and 9 officer tools, adding contacts, addresses, meetings, registrations, activities, alternates, external appointments, committees and user defined fields. The plugin reads the connector's tools live, so no configuration change is needed to pick them up.

## 1.0.0
- Initial release: Kube remote MCP connector — read-only tools for entity/officer search and detail, authenticated via OAuth 2.1 against `https://mcp.kube-platform.com`.
