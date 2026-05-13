<p align="center">
  <!-- Light-cone glyph from lightcone.dev: a stacked pair of triangles
       (past + future) sharing a common apex. The opacities mirror the
       site's logo-mark exactly. -->
  <svg width="56" height="56" viewBox="0 0 32 32" xmlns="http://www.w3.org/2000/svg" aria-label="Lightcone Research">
    <path d="M16 14 L7 3 L25 3 Z" opacity="0.8"/>
    <path d="M16 18 L7 29 L25 29 Z" opacity="0.35"/>
  </svg>
</p>

<h1 align="center">Lightcone Research</h1>

<p align="center">
  <em>Tools for transparent, reproducible and verifiable science.</em>
</p>
<p align="center">
  <a href="https://lightconeresearch.org">lightconeresearch.org</a> ·
  <a href="https://docs.lightconeresearch.org">documentation</a>
</p>

---

## What we work on

Computational research is full of methodological choices that quietly shape the results: how a dataset is filtered, how a model is parameterized, what cutoff defines an outlier. These choices are often defensible, often debatable, and almost always invisible by the time the paper is written.

We build tools that surface those choices, make them explicit, and let researchers explore the alternatives systematically — all the way from a research question down to materialized, integrity-checked results. Most of that machinery is driven by AI agents now, so a researcher can stay focused on the science instead of the plumbing.

## Our projects

### [ASTRA](https://github.com/LightconeResearch/ASTRA) &nbsp;·&nbsp; *Agentic Schema for Transparent Research Analysis*

A specification language and validator for analyses. One `astra.yaml` declares your inputs, outputs, methodological **decisions**, and the **prior insights** from the literature that justify each option. Includes the `astra` CLI, machine-verified evidence quotes, and the schema everything else builds on.

### [lightcone-cli](https://github.com/LightconeResearch/lightcone-cli) &nbsp;·&nbsp; *Agentic execution layer*

The `lc` command line, plus a Claude Code plugin (skills, agents, hooks) that turns an `astra.yaml` into materialized results. Recipes run through Snakemake on a Dask cluster — local laptop, SLURM allocation, or external scheduler. Every output gets a content-addressed manifest so `lc verify` can prove what you have on disk is what was actually computed.

## Try it in a couple lines

```text
uv tool install lightcone-cli
lc init my-analysis && cd my-analysis
claude                                   # opens Claude Code
# Inside Claude Code:
/lc-new                                  # scope a research question into astra.yaml
```

The [user guide](docs.lightconeresearch.org) walks you from there to your first reproducible result.

## Some core ideas

- **One spec, one truth.** `astra.yaml` is the single source of truth. Every input, output, recipe, and decision lives there.
- **Decisions, not defaults.** Every meaningful methodological choice is a named decision with options, a default, a rationale, and (where possible) literature evidence behind it.
- **Universes for free.** A *universe* is one specific selection of decision values. Sweep them to compare alternative defensible analyses side by side.
- **Provenance you can prove.** Every materialized output ships with a sidecar manifest recording the recipe, the container image, the decisions, the input chain, and content hashes. Tampering and drift are detectable, not hopeful.
- **Agents do the typing, you do the science.** The Claude Code plugin (`/lc-new`, `/lc-migrate`, `/lc-feedback`) handles the implementation grind so researchers can stay on the questions that matter.

## Talk to us

- 🐛 **Found a bug?**
  - Write an issue report using our provided templates.
  - Inside any Claude Code session, run `/lc-feedback <what went wrong>` and we get a clean issue with the context auto-attached.
- 📖 **Looking for the deeper docs?** Maintainer documentation lives inside the [main docs](https://docs.lightconeresearch.org) or in (`docs/`).

## Contributing

We welcome contributions across the stack — schema design, the agent surface, the execution engine, the docs, the rough edges you hit when you try to use any of this for real work. Each repo has a `docs/contributing/` directory with development setup and conventions. Smaller fixes are welcome as PRs without prior discussion; for larger changes, opening an issue first is appreciated.

## License

Our code ships under [BSD 3-Clause](https://opensource.org/license/BSD-3-Clause) unless a repository says otherwise. We aim to keep things permissively licensed so they can be used freely in academic and commercial research alike.

---

<sub>
Built with care by the Lightcone Research team and contributors.<br/>
If a tool here saves you a long afternoon of reproducibility paperwork,
that's the goal.
</sub>