# Lightcone Research

The open ecosystem for reproducible, composable, and verifiable scientific research in the age of agentic AI.

## Install

```bash
bash <(curl -fsSL https://lightconeresearch.github.io/lightcone.dev/install.sh)
```

Requires Python 3.11+ and git. Pass `--ssh` to clone via SSH.

## Quick Start

```bash
prism init my-analysis
cd my-analysis
claude
```

Then tell the agent `/prism-new` to scope your research question. It will walk you through identifying decisions, searching the literature, and producing a complete `astra.yaml` specification. When the spec is ready, `/prism-build` implements and runs it.

---

## The Stack

```
┌─────────────────────────────────────────┐
│       Prism-UI  (Visual Layer)          │  VS Code extension
├─────────────────────────────────────────┤
│       Prism  (Execution Layer)          │  Orchestration + Claude Code skills
├─────────────────────────────────────────┤
│       ASTRA  (Protocol Layer)           │  Declarative specification format
└─────────────────────────────────────────┘
```

### [ASTRA](https://github.com/LightconeResearch/ASTRA) — Protocol Layer

**Agentic Schema for Transparent Research Analysis**

ASTRA is the core specification format — a declarative schema that captures *what* an analysis does without prescribing *how* to run it. A single `astra.yaml` file defines the analysis: datasets, decision points, processing recipes, and expected outputs. Methodological choices (which estimator, what bin width, which prior) are first-class objects with linked justifications traced back to the literature or evidence. ASTRA enumerates every valid combination of these decisions, enabling multiverse analysis out of the box.

```
astra init      # scaffold a new analysis
astra validate  # check your spec against the schema
astra viz       # visualize the analysis DAG
astra universe  # list all decision-space universes
```

→ [README](https://github.com/LightconeResearch/ASTRA#readme) · [Design Doc](https://github.com/LightconeResearch/ASTRA/blob/main/DESIGN.md)

---

### [Prism](https://github.com/LightconeResearch/Prism) — Execution Layer

**The tooling and orchestration layer that lives on top of ASTRA**

Prism handles the full lifecycle of an analysis — scoping, implementation, execution, and workflow management. It ships Claude Code skills that let an AI agent design and build analyses conversationally, manages containerized execution across the multiverse, and tracks what has been materialized. The human stays in control while AI handles the scaffolding.

- **Claude Code skills** — `/prism-new` to scope an analysis interactively, `/prism-build` to implement it, `/prism-verify` to audit results
- **Execution backends** — Local, Docker, or SLURM HPC clusters
- **Multiverse execution** — Automatically runs recipes across every valid decision combination
- **Dagster integration** — Asset-based DAG execution with a web UI

```
prism init my-analysis   # create a new project
prism run                # execute all recipes
prism status             # check materialization progress
prism dev                # launch the Dagster web UI
```

→ [README](https://github.com/LightconeResearch/Prism#readme)

---

### [Prism-UI](https://github.com/LightconeResearch/Prism-UI) — Visual Layer

**Interactive canvas editor for ASTRA analyses**

Prism-UI is a VS Code extension that renders your analysis as an interactive node graph. Edit the spec visually, browse DOI-linked evidence for decisions, and explore results across the multiverse — all from within your editor. Changes in the canvas update `astra.yaml` in real time, and vice versa.

→ [README](https://github.com/LightconeResearch/Prism-UI#readme)

## License

All repositories are released under the [Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0).
