# Quenza (quenza)

Quenza is a digital care and client-engagement platform for coaches, therapists, and other helping professionals. Practitioners build activities - worksheets, exercises, psycho-education, intake forms, reflection prompts, and surveys - bundle them into timed pathways (care programs), and share them with clients through a branded client portal and mobile apps, then track responses, results, notes, tasks, and chat. Quenza was built by the founders of PositivePsychology.com and is based in Maastricht, Netherlands.

Quenza exposes a **documented public REST API (v1)** at [developers.quenza.com/docs/v1](https://developers.quenza.com/docs/v1), base URL `https://developers.quenza.com/v1`, authenticated with a workspace **Bearer token** generated under Settings -> Developer Tools -> API Token.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/quenza/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/quenza/refs/heads/main/apis.yml)

## Access Model (read this first)

- The v1 REST API is a **real, first-party public API**, but it is **plan-gated**: API access is included on the **Collective** and **Beyond** tiers only (not Spark, Growth, or Impact).
- Authentication is a single **workspace Bearer token**.
- The documented surface is **scoped to people and workflow**: Clients, Groups, Members (professionals), and Tasks.
- Quenza's UI has richer capabilities - building **activities**, **pathways/programs**, **assessments**, and reading **assessment results** - but **those have no documented public endpoints in v1**, so they are **not modeled as APIs here**. Nothing in this entry fabricates endpoints that Quenza does not publish.
- Quenza also offers **outbound webhooks** (HTTP callbacks) from the Growth plan up, but the webhook event catalog is not published in the OpenAPI reference and webhooks are not a WebSocket transport.

## Tags

- Coaching
- Therapy
- Client Engagement
- Digital Health
- Mental Health
- Practice Management
- Positive Psychology

## Timestamps

- **Created:** 2026-07-10
- **Modified:** 2026-07-10

## APIs

### Quenza Clients API

Programmatically manage the people a practitioner works with - list and retrieve clients (paginated), create a client and send an invitation email, update client fields, and archive or unarchive a client.

- **Human URL:** [https://developers.quenza.com/docs/v1](https://developers.quenza.com/docs/v1)
- **Base URL:** `https://developers.quenza.com/v1`
- **Confirmed endpoints:** `GET/POST /clients`, `GET/PATCH /clients/{client}`, `POST /clients/{client}/archive`, `POST /clients/{client}/unarchive`

### Quenza Groups API

Organize clients into groups for shared programs and communication - create a group and attach members to it.

- **Human URL:** [https://developers.quenza.com/docs/v1](https://developers.quenza.com/docs/v1)
- **Base URL:** `https://developers.quenza.com/v1`
- **Confirmed endpoints:** `POST /groups`, `POST /groups/{group}/members`

### Quenza Members API

Manage the team members (professionals) in a workspace - list all members including pending and suspended ones, invite a new member with a member or manager role, and update member fields.

- **Human URL:** [https://developers.quenza.com/docs/v1](https://developers.quenza.com/docs/v1)
- **Base URL:** `https://developers.quenza.com/v1`
- **Confirmed endpoints:** `GET/POST /members`, `PATCH /members/{professional}`

### Quenza Tasks API

List the tasks in a workspace (paginated), optionally filtered by assignee using `assignee_type` and `assignee_id` together.

- **Human URL:** [https://developers.quenza.com/docs/v1](https://developers.quenza.com/docs/v1)
- **Base URL:** `https://developers.quenza.com/v1`
- **Confirmed endpoint:** `GET /tasks`

## Common Properties

- [Website](https://quenza.com)
- [LinkedIn](https://www.linkedin.com/company/quenza)
- [Documentation](https://developers.quenza.com/docs/v1)
- [Support / Knowledge Base](https://help.quenza.com)
- [Plans](plans/quenza-plans-pricing.yml)
- [Rate Limits](rate-limits/quenza-rate-limits.yml)
- [Fin Ops](finops/quenza-finops.yml)

## Authentication

Bearer token in the `Authorization` header:

```
Authorization: Bearer {your-token}
```

Generate or regenerate the token in the Quenza workspace under **Settings -> Developer Tools -> API Token**.

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
