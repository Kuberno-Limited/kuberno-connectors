# Changelog

## 1.4.1
- Fix `icon.png`. The file had extra data after the end of the image, so Anthropic's plugin directory couldn't inspect it and held the plugin for review.

## 1.4.0
- Add the plugin's icon, and links to its documentation, support, privacy policy and terms of service, for its listing in Anthropic's plugin directory. These fields only affect the directory listing, so the plugin works as before.

## 1.3.0
- `search_officers` has a new `appointedEntityRegistrar` filter: the registrar of the entity an officer is appointed to, matching the Officers screen's "Appointed entity's registrar" filter. `registrar` is unchanged. It filters on the registrar that holds the officer's own profile, and its description now says so. For one officer the two often give different answers.
- `country` on `search_officers` now reads the appointed entity's own country, as the Kube screens do, instead of the countries covered by the entity's registrar. For most entities the answer is the same. `search_entities` has a new `country` filter that also reads the entity's own country. Its old `registrarCountry` filter is deprecated and will be removed in a later release. Until then it still filters on the countries covered by the entity's registrar.
- A country value of up to three letters is now matched only as an ISO code. Before, it was also matched as part of a country name, so `US` also matched Australia, Austria, Belarus, Cyprus and Russia. `UK` is not an ISO code; use `GB`.
- The filters are now checked against the field permissions the Kube screens use for them. The new `country` on `search_entities` is checked against the entity Country field; `registrarCountry` is still checked against the Registrar field. `registrar` on `search_officers` is now checked against the officer's Registrar field instead of the entity's. Every user can see that field, so `registrar` is no longer refused for users who cannot see the entity's Registrar field.
- The README's Search line names the new filter. The plugin reads tool schemas live, so no configuration change is needed.

## 1.2.0
- Refresh the Search line's filter description in the README: `search_entities` and `search_officers` now have far more filters than the six and four the line named, so it now names representative filters from each rather than an exhaustive list that goes stale every time the server gains one more. The connector reads tool schemas live, so this is a docs-only fix — no functional change.
- Add `get_my_activities` to the README under a new **My activities** grouping — it was missing entirely. It covers the signed-in user's own workload, theirs and their teams', across every entity they can see, distinct from `get_entity_activities`'s one named entity for whoever owns it.

## 1.1.0
- Document the full toolset in the README: 11 entity tools and 9 officer tools, adding contacts, addresses, meetings, registrations, activities, alternates, external appointments, committees and user defined fields. The plugin reads the connector's tools live, so no configuration change is needed to pick them up.

## 1.0.0
- Initial release: Kube remote MCP connector — read-only tools for entity/officer search and detail, authenticated via OAuth 2.1 against `https://mcp.kube-platform.com`.
