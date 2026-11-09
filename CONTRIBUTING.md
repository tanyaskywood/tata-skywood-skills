# Add or improve a skill

Keep each skill useful on its own, with a clear task, inputs, outcome and stopping conditions. Prefer improvements based on observed behavior over additional generic instructions.

## Add a skill

1. Create `skills/<lowercase-hyphenated-name>/SKILL.md` with a matching `name` and a concise `description` in YAML frontmatter. Use plain, single-line values for these two fields so the lightweight repository checker can read them.
2. Add a `README.md` describing when to use it, what to provide, what it produces, how to start, requirements and limitations. Add a small synthetic example. Include references or executable helpers only when needed.
3. Add an entry to `catalogue.json`, using the existing entry as the schema example. Choose an existing category when it fits; add a new category when needed. Keep the skill's folder stable even if its category changes.
4. Start at version `0.1.0` and status `experimental`. Record the review date as `YYYY-MM-DD`. Increment the minor version for new behavior, patch for corrections, and major for breaking workflow changes once stable.
5. Run the commands below and review the generated catalogue and rendered website. Add a brief entry to `CHANGELOG.md` for behavior changes.
6. Open a pull request with the problem, intended result and checks performed. Do not commit real customer information, credentials, account exports, or copied third-party skills without appropriate permission and attribution.

## Local commands

Python 3.9 or newer is sufficient. No packages need to be installed.

```sh
python3 scripts/catalogue.py
python3 scripts/catalogue.py --check
python3 -m http.server 8000 --directory docs
```

Open `http://localhost:8000` to review the catalogue. The first command regenerates `CATALOGUE.md` and `docs/index.html` from `catalogue.json` and `docs/catalogue-template.html`. The check command validates required metadata, matching skill folders, basic name/description frontmatter, local Markdown link targets and generated-file freshness. It exits nonzero on errors and writes nothing in check mode. It is a repository consistency check, not a complete YAML or Agent Skills specification validator.

GitHub Pages serves the committed `docs/` directory from `main`. Publishing a catalogue update requires committing the regenerated files; no separate frontend build or runtime service is involved.

## Review behavior, not just formatting

For a new skill, try a realistic request with complete context, a request missing important inputs, and an edge case likely to produce an unsupported answer. Record what actually happened, with enough detail to reproduce it. Do not mark a skill field-tested from a structural check or an illustrative example.

For Bullseye Marketing, check that an empty-context request produces the interview and waits; a pre-revenue product does not acquire invented CAC evidence; and zero paid conversions do not produce a declared winner.

Use only the permissions the user granted. A planning skill should not silently become permission to publish, contact people or spend money. Preserve source attribution when adapting methods, and distinguish examples from measured results.

## Catalogue fields

| Field | Meaning |
| --- | --- |
| `id` | Stable folder name and invocation identifier |
| `name`, `summary` | Human-facing title and outcome |
| `category`, `tags` | Browse grouping and search keywords |
| `version` | Semantic version of the workflow |
| `status` | `experimental`, `field-tested` or `deprecated` |
| `reviewed` | Most recent actual review date |
| `inputs`, `outputs` | What a user brings and receives |
| `start_prompt` | Copyable first request |

By submitting a contribution, you agree that it may be distributed under this repository's [MIT License](LICENSE). Preserve third-party attribution and include only material you have permission to contribute.
