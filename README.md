# Unbabel (unbabel)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Unbabel is a Language Operations (LangOps) platform that combines always-on AI translation with on-demand human review to localize customer support, marketing, and other business content at scale. Its long-standing developer surface is the Unbabel Translation API (tapi/v2, base `https://api.unbabel.com/tapi/v2`), an asynchronous REST API where callers submit text with a source/target language pair, tone, and topic, then retrieve the completed AI-plus-human translation by uid or via a callback. Unbabel also offers a pure machine-translation path (`mt_translation`) and helper resources for language pairs, tones, topics, word count, and account details. Unbabel has since launched the standalone LLM-based product Widn.AI (its own RESTful API at widn.ai) and, following its combination with TransPerfect, its research and models (TowerLLM, COMET, Widn.AI) now also feed the GlobalLink platform; the tapi/v2 Translation API remains the documented developer surface at developers.unbabel.com.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/unbabel/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/unbabel/refs/heads/main/apis.yml)

## Authentication

Requests use a token header of the form `Authorization: ApiKey <username>:<api_key>`. The production base URL is `https://api.unbabel.com/tapi/v2`; a sandbox is available at `https://sandbox.unbabel.com/tapi/v2`.

## Tags

- Translation
- Localization
- Language Operations
- LangOps
- Machine Translation
- Human in the Loop
- AI

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### Unbabel Translation API

Asynchronously submit text for AI-plus-human translation and manage the resulting translation jobs. Create a translation with a source/target language pair, tone, topic, and optional callback URL, then list jobs by status or retrieve a specific job by uid to read the completed translated text, price, and status.

- **Human URL:** [https://developers.unbabel.com/docs/introduction](https://developers.unbabel.com/docs/introduction)
- **Base URL:** `https://api.unbabel.com/tapi/v2`

### Unbabel Machine Translation API

Request pure machine translation (no human review) via the `mt_translation` resource, list MT jobs by status, retrieve a specific MT job by uid, and optionally upgrade a machine translation to a full human-reviewed translation.

- **Human URL:** [https://developers.unbabel.com/docs/introduction](https://developers.unbabel.com/docs/introduction)
- **Base URL:** `https://api.unbabel.com/tapi/v2`

### Unbabel Language Pairs API

List the source-to-target language pairs Unbabel can translate, optionally filtered by a set of training languages. Used to validate a requested language combination before submitting a translation.

- **Human URL:** [https://developers.unbabel.com/reference/language-pair](https://developers.unbabel.com/reference/language-pair)
- **Base URL:** `https://api.unbabel.com/tapi/v2`

### Unbabel Tone and Topic API

List the tones (for example formal or friendly) and topics/domains available for a translation, so callers can steer register and subject-matter context when submitting text.

- **Human URL:** [https://developers.unbabel.com/reference/tone](https://developers.unbabel.com/reference/tone)
- **Base URL:** `https://api.unbabel.com/tapi/v2`

### Unbabel Word Count API

Calculate the billable word count for a block of text before submitting it for translation, letting callers estimate cost and volume against their plan.

- **Human URL:** [https://developers.unbabel.com/reference/word-count](https://developers.unbabel.com/reference/word-count)
- **Base URL:** `https://api.unbabel.com/tapi/v2`

### Unbabel Account API

Retrieve the authenticated customer account's information, including identity and balance/usage details, for the API credentials in use.

- **Human URL:** [https://developers.unbabel.com/reference/account](https://developers.unbabel.com/reference/account)
- **Base URL:** `https://api.unbabel.com/tapi/v2`

### Unbabel Notifications API

Because translation is asynchronous, callers can supply a `callback_url` when creating a translation and Unbabel will POST a notification to that HTTP endpoint when the job changes status (for example completed). This is a server-to-endpoint webhook callback, not a WebSocket; the exact payload shape is modeled from the documented callback behavior.

- **Human URL:** [https://developers.unbabel.com/docs/introduction](https://developers.unbabel.com/docs/introduction)
- **Base URL:** `https://api.unbabel.com/tapi/v2`

## Common Properties

- [GitHub Organization](https://github.com/Unbabel)
- [LinkedIn](https://www.linkedin.com/company/unbabel)
- [Website](https://unbabel.com)
- [Documentation](https://developers.unbabel.com)
- [Plans](plans/unbabel-plans-pricing.yml)
- [Rate Limits](rate-limits/unbabel-rate-limits.yml)
- [Fin Ops](finops/unbabel-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
