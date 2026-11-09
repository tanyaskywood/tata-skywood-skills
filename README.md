<p align="center"><img src="assets/banner.svg" alt="tata@skywood Skills — Practical workflows for thoughtful AI work" width="100%"></p>

# tata@skywood Skills

**Reusable AI workflows for turning context into decisions and practical next steps.**

A growing collection maintained by [Tanya](https://github.com/tanyaskywood). Each skill describes how an AI assistant should approach a specific task: what to ask, which evidence to use, what to produce, and when to wait for you.

[Browse the catalogue](CATALOGUE.md) · [Visual catalogue](https://tanyaskywood.github.io/tata-skywood-skills/) · [Get started](#get-started) · [Add a skill](CONTRIBUTING.md)

## Start with a problem

| I want to… | Try this skill | What I get |
| --- | --- | --- |
| Find the right marketing channels for my product | [Bullseye Marketing](skills/bullseye-marketing/README.md) | A founder interview, 19 channel ideas, three test candidates and daily two-week plans |

**First release:** one skill, with room for more. The [full catalogue](CATALOGUE.md) records category, version, maturity and review date. The [visual catalogue](https://tanyaskywood.github.io/tata-skywood-skills/) supports search, category filters and sorting.

## Get started

### In Codex

Ask the skill installer to install just the skill you want:

```text
Use $skill-installer to install https://github.com/tanyaskywood/tata-skywood-skills/tree/main/skills/bullseye-marketing
```

Then start a new turn and ask:

```text
Use $bullseye-marketing for my product. Interview me first and ask for my product and GTM sources before recommending channels.
```

If your client does not discover it immediately, restart it. An existing installation may need an explicit update rather than another install; keep local customizations before replacing it.

### In another assistant

The folders use the [Agent Skills format](https://agentskills.io/specification). Install the complete skill folder using your assistant's supported skill workflow. `SKILL.md` is the entry point; keep its `references/` alongside it. `agents/openai.yaml` supplies Codex-specific display metadata.

You can also share the entry point and reference files in a chat and ask the assistant to follow them. This is a manual workflow, not an installed integration. Other assistants have not been tested with this bundle; source access and browsing depend on your environment.

## Featured: Bullseye Marketing

**Choose where to test before deciding where to scale.**

1. Answer 10 tailored questions and share product/GTM evidence.
2. Review a customized brief with facts and assumptions separated.
3. Explore all 19 channels and select three promising experiments.
4. Follow a daily 14-day plan for each candidate, within your cash and time limits.
5. Return with results to assess whether a channel deserves more investment.

The skill waits for interview answers. It treats estimated acquisition cost as an estimate, and leaves the winning channel undecided until customer evidence supports a decision. It prepares plans; it does not launch campaigns or spend money.

[Read the skill overview](skills/bullseye-marketing/README.md) · [Inspect the instructions](skills/bullseye-marketing/SKILL.md) · [See an example start](skills/bullseye-marketing/examples/first-session.md)

## How the library grows

```text
skills/<skill-name>/       One self-contained, installable skill
  SKILL.md                Agent instructions and discovery metadata
  README.md               Human-facing overview and usage
  references/             Supporting guidance, when needed
  examples/               Clearly labelled examples
  agents/openai.yaml      Optional Codex display metadata
catalogue.json            Searchable metadata for every published skill
CATALOGUE.md               Generated GitHub catalogue
docs/                     Static visual catalogue; no build dependencies
scripts/catalogue.py      Validate and regenerate both catalogue views
```

Stable skill paths keep installation links working as the catalogue grows. Categories and tags belong in the catalogue, so adding a category does not require moving existing folders. Start at [CONTRIBUTING.md](CONTRIBUTING.md) for the addition and review process.

## Quality and status

**Experimental** means the package and instructions have been reviewed, but broad real-world performance is not established. **Field-tested** requires documented scenarios and observed results. **Deprecated** means retained for reference, with a replacement or explanation. A valid file format does not prove a workflow's effectiveness.

Bullseye Marketing is experimental. Its original package passed the Codex skill validator; this repository also checks catalogue consistency and local Markdown links. The workflow has not yet been independently evaluated across products or assistants.

## Help and contributions

[Open an issue](https://github.com/tanyaskywood/tata-skywood-skills/issues/new/choose) to suggest a skill or report a problem. Include the skill version, assistant, relevant prompt and expected versus observed behavior. Use synthetic or redacted examples rather than private customer data.

## Sources and credits

Repository patterns were informed by [Anthropic's skills collection](https://github.com/anthropics/skills), [OpenAI's plugin examples](https://github.com/openai/plugins), and [GitHub's README guidance](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes). This is an independent collection, not an official OpenAI or Anthropic product. These examples informed the structure; this repository does not package a plugin marketplace.

Bullseye Marketing adapts the user-supplied Oskar Bader session summary and prompt. The original Bullseye framework comes from *Traction* by Gabriel Weinberg and Justin Mares. See the [skill attribution](skills/bullseye-marketing/SKILL.md#attribution) for details.

## License

This collection is licensed under the [MIT License](LICENSE). You may use, adapt and share the skills, including commercially, provided you retain the copyright and license notice. Third-party references remain subject to their respective rights.
