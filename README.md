# Relational Curriculum Geometry

**Relational Curriculum Geometry** is a research hypothesis and experimental framework for testing whether the structure, order, proximity, and relational positioning of training data affects how small language models learn, reason, transfer concepts, surface uncertainty, and handle multithread tasks.

The core idea is simple:

> A model does not only learn what data contains.
>
> It may also learn how concepts live beside, above, below, before, after, and across from each other.

This project explores whether better curriculum structure can produce cleaner model behaviour than ordinary bulk data exposure.

---

## Core Hypothesis

LLM capability is shaped not only by dataset size and data quality, but also by **relational curriculum geometry**.

That includes:

- what concepts are learned first,
- what concepts are grouped together,
- what examples are treated as prerequisites,
- what examples are treated as boundary cases,
- what domains are bridged,
- how uncertainty is represented,
- how tool-use and role authority are taught,
- and how multiple reasoning threads are staged for comparison.

In short:

> Not just more bricks.
>
> Better rooms, roads, walls, doors, and limbs.

---

## Why This Matters

Most LLM training treats data as a large-scale prediction substrate.

This project asks a narrower question:

> If two models see the same examples, but one sees them in a staged relational curriculum and the other sees them in random order, do they learn differently?

If the answer is yes, then dataset sorting is not merely housekeeping.

It becomes a possible model-shaping instrument.

---

## Relationship To Janet School

This project follows the same broad doctrine as **Janet School**.

Janet School does not throw random curriculum at a learner. It stages learning through a signal ladder:

```text
recall -> rule use -> near transfer -> cross-representation -> composition -> abstraction candidate
```

Relational Curriculum Geometry applies a similar idea to LLM training data.

Instead of dumping examples into the model, the data is arranged so that simpler concepts can support more complex ones.

---

## Relationship To Venom Shell

Venom Shell-style reasoning requires a model to hold multiple reasoning threads at once and compare them cleanly.

Example threads might include:

- user intent,
- task goal,
- domain knowledge,
- uncertainty,
- tool limits,
- host permissions,
- prior failure patterns,
- safety constraints,
- and final output requirements.

The hypothesis is that structured curriculum data may help these threads become cleaner internal handles, reducing the cost of picking them up later during reasoning.

---

## The Three Desired Model Changes

This project is also connected to three desired behavioural changes for safer and more useful models.

### 1. Correctness Over Speed

The model should learn to slow down when stakes, uncertainty, or complexity rise.

### 2. Surface Uncertainty

The model should expose missing evidence, weak assumptions, ambiguity, and unverifiable claims instead of pretending certainty.

### 3. Team Member, Not Whole Team

The model should understand itself as one role-specific participant inside a larger system.

Other participants may include:

- the user,
- peer AI systems,
- the host environment,
- tools,
- reviewers,
- files,
- logs,
- and external authorities.

The model should not collapse all responsibility into itself.

---

## Experiment 001

The first proposed experiment compares small models or fine-tunes trained on the same content in different structures.

### Group A: Random Baseline

Cleaned examples in random order.

### Group B: Domain Grouped Baseline

Examples grouped by broad topic.

### Group C: Complexity Curriculum

Examples grouped by topic and ordered from basic to complex.

### Group D: Full Relational Curriculum

Examples grouped by domain, complexity, relation type, boundary case, uncertainty state, tool-use relevance, and role structure.

---

## Example Test Domain

The first narrow test domain is likely to be:

```text
basic programming and debugging
```

This domain is useful because it allows clear tests for:

- recall,
- rule use,
- near transfer,
- cross-representation transfer,
- boundary detection,
- uncertainty surfacing,
- tool-use discipline,
- role discipline,
- and multithread reasoning.

---

## Evaluation Targets

The project is not primarily about beating broad benchmarks.

It is focused on behaviours that should be affected by curriculum geometry:

- better learning per token,
- better transfer,
- better boundary-case handling,
- better uncertainty calibration,
- better role separation,
- better tool-use discipline,
- better multithread reasoning,
- lower prompt scaffolding requirements,
- and more legible failure patterns.

---

## Falsifiability

This hypothesis should be weakened if controlled tests show that structured curriculum data provides no meaningful advantage over randomly ordered data when token count, model size, data quality, contamination, and training settings are controlled.

The goal is not to prove a belief.

The goal is to make the belief testable.

---

## Project Documents

Recommended starting documents:

```text
HYPOTHESIS.md
EXPERIMENT_001.md
README.md
LICENSE
```

Possible future documents:

```text
DATASET_SCHEMA.md
SORTER_GUIDE.md
EVAL_BATTERY.md
FAILURE_TAXONOMY.md
RESULTS_TEMPLATE.md
JANET_SCHOOL_BRIDGE.md
VENOM_SHELL_BRIDGE.md
```
- [GLOSSARY.md](GLOSSARY.md)

---

## Status

Early-stage hypothesis and experiment design.

This repository is intended to capture the testable shape of the idea before implementation hardens around assumptions.

---

## License

This project is released under the **GNU Affero General Public License v3.0**.

See [`LICENSE`](LICENSE) for details.

---

## Author

Created by **Instance001 / Fractal Media Infrastructure**.

This project is part of a broader local-first research and tooling ecosystem exploring model evaluation, structured learning, tool discipline, human-AI teaming, and practical AI safety architecture.
