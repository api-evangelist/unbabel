# Unbabel (unbabel)

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
