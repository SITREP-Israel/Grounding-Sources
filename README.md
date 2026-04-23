# Grounding-Sources

Public inventory of the data sources that [SITREP ISR](https://sitrepisr.com) monitors to generate its situation reports.

This repo exists so that:

- Anyone can see **which sources feed the pipeline**, how they are monitored, and how they are categorised.
- Researchers, journalists, and contributors can **suggest new sources** (or flag issues with existing ones) via a public, reviewable process.
- The provenance of SITREP ISR reports is auditable — no black-box source list.

> This repo is an **inventory and proposal surface**, not the live whitelist. The production source list lives in the SITREP ISR database and is updated by maintainers from the material here.

## Layout

```
sources/
  official-gov/
  israeli-media/
  iran-state-media/
  arab-gulf-media/
  western-wire/
  social-telegram/
  osint/
  other/
CONTRIBUTING.md           How to propose a new source or edit an existing one
schema/source.schema.yml  Canonical shape of a source entry
.github/ISSUE_TEMPLATE/   Source-suggestion and source-issue templates
```

Each source is a single YAML file under the category folder it belongs to. File name is the source slug (e.g. `reuters.yml`).

## Categories

| Slug | Description |
|---|---|
| `official_gov` | Government ministries, militaries, IGOs |
| `israeli_media` | Israeli domestic press (English or translated) |
| `iran_state_media` | Iranian / Iran-aligned state outlets |
| `arab_gulf_media` | Arab and Gulf press |
| `western_wire` | Wire services (Reuters, AP, AFP) |
| `western_media` | Major Western outlets (BBC, NYT, WSJ, Guardian, etc.) |
| `social_telegram` | Monitored Telegram channels |
| `osint` | OSINT analysts and conflict-tracking aggregators |
| `think_tank` | Research institutes and policy shops |
| `dissident` | Diaspora / opposition outlets covering closed regimes |
| `other` | Anything that doesn't fit the above |

## Monitoring methods

Each source entry declares how it is ingested. Current methods:

- `rss` — pulled from a published RSS/Atom feed
- `scrape` — HTML scrape of a homepage or listing page
- `telegram` — Telegram channel scrape (public channels only)
- `exa` — surfaced via the Exa search index with a domain filter
- `manual` — operator-supplied URL only (not auto-polled)

## The `propaganda` flag

Each source entry carries an optional `propaganda: true | false` boolean. It marks sources that are state-controlled or state-aligned and routinely publish material intended to shape opinion on behalf of a state or armed actor (e.g. IRNA, Press TV, Al-Masirah). The flag is **not** a judgement of truthfulness — propaganda sources are monitored precisely because adversary framing is itself signal. It is used in the SITREP ISR reader UI to annotate where a claim originated.

## Suggesting a source

Open an [issue](../../issues/new/choose) using the **"Suggest a source"** template, or open a PR adding a YAML file under the right category. See [CONTRIBUTING.md](CONTRIBUTING.md).

## Licence

Inventory metadata in this repo is released under CC0 / public domain. Linked source content remains the property of its respective publishers.
