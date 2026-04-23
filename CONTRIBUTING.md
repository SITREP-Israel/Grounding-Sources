# Contributing

Thanks for helping improve SITREP ISR's source coverage.

## Two ways to contribute

### 1. Open an issue (lowest friction)

Use the **"Suggest a source"** or **"Flag a source issue"** issue template. A maintainer will validate and either add it directly or ask you to open a PR.

### 2. Open a pull request

1. Fork this repo.
2. Create a YAML file under `sources/<category>/<slug>.yml`. Slug is lowercase-kebab (e.g. `al-jazeera`, `times-of-israel`).
3. Fill it in against [`schema/source.schema.yml`](schema/source.schema.yml). See [`sources/_example.yml`](sources/_example.yml).
4. Open the PR. CI (planned) will validate the YAML shape.

## What makes a good source

We're biased toward sources that are:

- **Primary or first-order** — official ministries, militaries, wire services, direct-reporting outlets.
- **Reachable programmatically** — has RSS, a stable HTML layout, or a public Telegram channel.
- **Identifiable** — a clear publisher, not an anonymous aggregator.
- **English or readily translatable** — the pipeline's LLM stage handles non-English but the editorial output is English.

We're cautious about:

- Pure aggregators that republish wire copy (duplicates noise).
- Anonymous OSINT accounts without track record.
- Sources with paywalls that block programmatic fetch.

Inclusion in this repo is **not** an endorsement of a source's editorial line. The pipeline is explicitly designed to ingest adversarial sources (e.g. Iranian state media) so their framing can be surfaced and contrasted.

## Flagging an issue with an existing source

Open a **"Flag a source issue"** issue. Useful reports include:

- The source has changed its feed URL or layout and the scrape is broken.
- The source has ceased publication or pivoted away from the beat.
- Miscategorisation (e.g. listed as `western_wire` but really state-affiliated).
- Duplicate entries.

## What this repo is not

- **Not the live whitelist.** The production pipeline's source list lives in the SITREP ISR database. Maintainers reconcile this repo into the DB on a cadence.
- **Not a place for story tips.** Tips go to the SITREP ISR contact channel, not here.
