# Quenza (quenza)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
