<div align="center">
  <img src="https://lightconeresearch.org/img/logo-primary.svg" alt="Lightcone logo and wordmark" height="200" style="max-width: 100%">
</div>

<p align="center">
  <em>Tools for transparent, reproducible and verifiable science.</em>
</p>

<p align="center">
  <a href="https://docs.lightconeresearch.org"><img src="https://img.shields.io/badge/Documentation-docs.lightconeresearch.org-334155?style=for-the-badge" alt="Documentation"></a>
  <a href="https://docs.lightconeresearch.org/quickstart"><img src="https://img.shields.io/badge/Quick_start-get_started-426b78?style=for-the-badge" alt="Quick start"></a>
  <a href="https://discord.gg/EbG6JKuyAx"><img src="https://img.shields.io/badge/Discord-join_us-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Discord"></a>
</p>

<p align="center">
  <a href="https://lightconeresearch.org">lightconeresearch.org</a>
</p>

---

## What we work on

Computational research is full of methodological choices that quietly shape the results: how a dataset is filtered, how a model is parameterized, what cutoff defines an outlier. These choices are often defensible, often debatable, and almost always invisible by the time the paper is written.

We build open tools that make those choices explicit and keep the record for you: your AI agent plans the analysis with you, records each decision with the evidence behind it, and every result comes from a recorded run you can trace back and reproduce months later.

## Quick start

1. Install [`uv`](https://docs.astral.sh/uv/getting-started/installation/), version **0.12 or later** (check with `uv --version`).
2. Point your favorite coding agent (Claude Code, Codex, …) at our skills repository and let it install the skills and plugins itself:

   ```text
   Install the Lightcone skills and plugins from https://github.com/LightconeResearch/agent-skills
   ```

   The Lightcone plugin then installs the Lightcone CLI it needs on first use.

   > [!WARNING]
   > You may need to reload the plugins (or restart your agent) before they work.

Then start your agent in an empty directory and give it your research question:

```text
I want to start a new Lightcone analysis: <your research question>
```

The words "new analysis" are enough for your agent to pick up the Lightcone skill. It works through the plan with you, records every decision in an `astra.yaml`, then runs the analysis with full provenance.

👉 **[Follow the full quick start](https://docs.lightconeresearch.org/quickstart)** for the next steps, including exploring your project in JupyterLab.

## Our projects

These projects are in early alpha and evolve quickly: interfaces may change between releases. Bug reports and feedback are very welcome.

| | Project | What it does |
|---|---|---|
| **Specification** | [astra-spec](https://github.com/LightconeResearch/astra-spec), [astra-tools](https://github.com/LightconeResearch/astra-tools) | ASTRA (*Agentic Schema for Transparent Research Analysis*), a declarative YAML format for an analysis's inputs, outputs, decisions and evidence, plus the `astra` CLI to validate it. Docs at [astra-spec.org](https://astra-spec.org). |
| **Workflow** | [lightcone-cli](https://github.com/LightconeResearch/lightcone-cli) | The `lc` execution layer: turns an `astra.yaml` into results across every universe of decisions, in locked environments, locally or on Slurm, with a provenance record for every output. |
| **Agentic** | [agent-skills](https://github.com/LightconeResearch/agent-skills), [feedback](https://github.com/LightconeResearch/feedback) | Plugins that teach Claude Code, Codex and other agents the Lightcone stack, following the open [Agent Skills](https://agentskills.io) standard, plus a feedback plugin that turns bug reports and suggestions from your agent session into issues on the right repository. |
| **Interface** | [Lightcone Lab](https://github.com/LightconeResearch/jupyterlab-lightcone) | An AI-assisted research workbench for JupyterLab: explore your analysis, trace every result back to the run that made it, and work alongside your agent. |
| **Publication** | [MySTRA](https://github.com/LightconeResearch/MySTRA) | Write papers and reports on top of ASTRA analyses in plain [MyST](https://mystmd.org/) Markdown, with decisions, figures and numbers pulled in by reference. |

## Some core ideas

- **One spec, one truth.** `astra.yaml` is the single source of truth. Every input, output, recipe, and decision lives there.
- **Decisions, not defaults.** Every meaningful methodological choice is a named decision with options, a default, a rationale, and (where possible) literature evidence behind it.
- **Provenance you can prove.** Every output is committed together with a content-addressed manifest and a re-runnable run record. Tampering and drift are detectable, not hopeful.
- **Agents do the typing, you do the science.** The agent handles the implementation grind; you make the scientific choices.

## Community

- **Questions, ideas, or want to try the stack on your own research?** Come talk to us on **[Discord](https://discord.gg/EbG6JKuyAx)**.
- **Found a bug?** Two ways to report it:
  - Open an issue using our templates.
  - From your agent session, install the [Lightcone Feedback](https://github.com/LightconeResearch/feedback) plugin and ask: *"Use Lightcone Feedback to report this: …"*. It drafts the issue for your approval and routes it to the right repository.
- **Looking for the deeper docs?** Everything is on [docs.lightconeresearch.org](https://docs.lightconeresearch.org).
- **Want to contribute?** We welcome contributions across the stack: schema design, the agent surface, the execution engine, the docs, and the rough edges you hit when you use any of this for real work. Check a repository's `CONTRIBUTING.md`, where it has one, for development setup and conventions. Smaller fixes are welcome as PRs without prior discussion; for larger changes, opening an issue first is appreciated.

## License

Our code ships under [BSD 3-Clause](https://opensource.org/license/BSD-3-Clause) unless a repository says otherwise. We aim to keep things permissively licensed so they can be used freely in academic and commercial research alike.

---

<sub>
Built with care by the Lightcone Research team and contributors.<br/>
If a tool here saves you a long afternoon of reproducibility paperwork,
that's the goal.
</sub>
