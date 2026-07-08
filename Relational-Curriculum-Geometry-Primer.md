HYPOTHESIS.md

Relational Curriculum Geometry Hypothesis

Summary

The Relational Curriculum Geometry Hypothesis proposes that LLM capability is shaped not only by the amount and quality of training data, but also by the structure, order, proximity, and relational positioning of that data during training.

In simpler terms:

«A model does not only learn what data contains.
It also learns how concepts live beside, above, below, before, after, and across from each other.»

If data is fed as an unordered bulk dump, the model may still learn useful patterns, but it may need to spend more internal compute reconstructing relationships between concepts later.

If data is organized as a staged curriculum, the model may form cleaner internal conceptual pathways. This may improve learning efficiency, transfer, uncertainty handling, role discipline, and multithread reasoning.

---

Core Claim

Training data is not just content.

Training data is also geometry.

The way examples are grouped, ordered, contrasted, repeated, scaffolded, and connected may influence the internal structures a model develops.

A well-structured dataset may help build cleaner latent-space organization:

- basic concepts before compound concepts,
- related domains near each other,
- prerequisite ideas before dependent ideas,
- boundary cases near ordinary cases,
- uncertainty examples near ambiguous cases,
- role examples near tool-use and authority examples,
- cross-domain bridges between concept families,
- and multithread examples after the model has clean handles for individual threads.

This may let a model spend less effort searching, untangling, and reconstructing context, leaving more compute available for reasoning.

---

Short Version

More data is not always the same as better learning.

A model trained on a messy pile may learn the same facts as a model trained on a structured curriculum, but the structured model may learn cleaner access paths between those facts.

The hypothesis is:

«Structure improves the usefulness of data by teaching relationships, not merely content.»

---

Metaphor

The dataset is not just a pile of bricks.

It can also be a city plan.

- Examples are bricks.
- Domains are rooms.
- Prerequisites are foundations.
- Relations are doors.
- Transfer examples are roads.
- Boundary cases are walls.
- Tool-use examples are limbs.
- Uncertainty examples are fog markers.
- Role examples define who is allowed to touch what.
- Multithread examples teach the model to pick up several objects at once and compare them.

The goal is not merely to feed the model more bricks.

The goal is to build better rooms, roads, walls, doors, and limbs.

---

Janet School Parallel

This hypothesis follows the same broad doctrine as Janet School.

Janet School does not throw random curriculum at a learner. It stages learning through increasing complexity:

«recall → rule use → near transfer → cross-representation → composition → abstraction candidate»

The same principle may apply to LLM building.

Instead of feeding a model unstructured text, the dataset sorter can arrange material into a staged curriculum:

«primitive concept → simple example → rule use → near transfer → boundary case → cross-domain bridge → role/tool example → uncertainty case → multithread reasoning task»

The point is not to make the model memorize a school curriculum.

The point is to shape how concepts become reachable, comparable, and usable.

---

Why This Might Matter

1. Reduced routing waste

A model may waste less inference compute finding and reconnecting concepts if those concepts were learned in a clean relational structure.

Messy data forces reconstruction.

Structured data may provide a map.

---

2. Cleaner concept handles

A staged curriculum may help concepts become cleaner internal objects.

For example, a model may learn:

- cause,
- exception,
- analogy,
- contradiction,
- uncertainty,
- role boundary,
- tool authority,
- and final human approval

as distinct but related concepts, rather than tangled patterns.

---

3. Better transfer

If a concept is deliberately shown across prose, dialogue, code, tables, structured data, and edge cases, the model may learn the underlying relation rather than only surface wording.

---

4. Better uncertainty handling

If ambiguous and insufficient-evidence cases are treated as first-class curriculum items, the model may learn that uncertainty is not a failure mode.

It is a valid state to surface.

---

5. Better role discipline

If the model repeatedly sees tasks where the user, assistant, host, tool, reviewer, and external authority each have different responsibilities, it may better learn that it is not the whole system.

This supports the design principle:

«Team member, not whole team.»

---

6. Better multithread reasoning

Venom Shell-style reasoning requires the model to hold several active threads at once.

For example:

- user intent,
- domain facts,
- uncertainty,
- tool limits,
- host permissions,
- previous failure pattern,
- safety constraints,
- and final output requirements.

If those threads were learned as separable but connected structures, the model may be able to pick them up more cleanly and reason across them at lower cost.

---

Relationship To The Three Desired Model Changes

This hypothesis supports three proposed behavioural changes for safer and more useful models.

1. Correctness over speed

The model should learn to slow down when stakes, uncertainty, or complexity rise.

This should not merely be a prompt instruction. It should be trained into the model as a routing preference.

---

2. Surface uncertainty

The model should reveal doubt, missing information, weak evidence, ambiguity, and unverifiable assumptions.

Uncertainty should be represented as a useful internal state, not as a disclaimer pasted onto the end of an answer.

---

3. Team member, not whole team

The model should understand itself as one role-specific actor inside a larger system.

Other actors may include:

- the user,
- other AI systems,
- the host environment,
- tools,
- files,
- reviewers,
- external authorities,
- and final human decision-makers.

The model should not collapse all responsibility into itself.

---

Predictions

If the Relational Curriculum Geometry Hypothesis is correct, then models trained or fine-tuned on structured curriculum data should show measurable improvements over models trained on the same content in random or weakly structured order.

Possible improvements include:

1. Better learning per token.
2. Better near-transfer performance.
3. Better cross-domain transfer.
4. Better boundary-case detection.
5. Better uncertainty surfacing.
6. Better tool-use discipline.
7. Better role-boundary awareness.
8. Better multithread reasoning.
9. More legible failure patterns.
10. Less prompt scaffolding required at inference time.

The hypothesis does not require structured models to win every benchmark.

It specifically predicts gains in tasks that require relation handling, transfer, boundary recognition, role discipline, and multithread coordination.

---

Falsification Conditions

The hypothesis should be weakened if controlled experiments show that structured curriculum data provides no meaningful advantage over randomly ordered data.

It should also be weakened if:

1. Gains disappear when data quality and token count are controlled.
2. Structured models only memorize labels without improving transfer.
3. Complexity ordering provides no benefit over random ordering.
4. Boundary-case training does not improve boundary detection.
5. Uncertainty training does not improve uncertainty calibration.
6. Role-labeled training does not improve role discipline.
7. Multithread reasoning does not improve after structured curriculum training.
8. Observed gains are explained entirely by benchmark contamination, duplicate examples, or cleaner writing rather than relational structure.

This hypothesis must be tested, not assumed.

---

Confounders To Control

Experiments should document or control:

- total token count,
- model architecture,
- training duration,
- learning rate,
- dataset quality,
- duplicate examples,
- benchmark leakage,
- source contamination,
- example length,
- instruction format,
- sorting-model bias,
- label leakage,
- domain imbalance,
- and whether gains come from structure or simply cleaner text.

A useful control is to use the same structured dataset but shuffle the order.

Another useful control is to preserve domain grouping while removing complexity staging and relation labels.

---

Role Of The Dataset Sorter

The LLM Semantic Dataset Sorter is not merely a file organizer.

It is a curriculum compiler.

Its job is to arrange training data by:

- domain,
- complexity,
- prerequisite relation,
- concept family,
- analogy,
- contrast,
- exception,
- boundary case,
- uncertainty case,
- role type,
- tool-use relevance,
- safety relevance,
- transfer target,
- and multithread usefulness.

The sorter should also preserve “does not fit” examples.

Anomalies and boundary cases may be especially valuable because they teach the model where categories break.

---

Proposed Closed Loop

The long-term loop is:

«sorter → curriculum → model → test chamber → telemetry → improved sorter»

A model is trained or fine-tuned on structured curriculum data.

Janet School-style tests then evaluate concept acquisition, transfer, abstraction, uncertainty, and boundary handling.

Failures are fed back into the sorter.

The sorter adds missing prerequisites, clearer bridges, better boundary cases, or improved role examples.

The next model is trained on an improved curriculum.

---

Working Summary

The Relational Curriculum Geometry Hypothesis proposes that LLM training data should be treated as structured curriculum, not merely text volume.

Data matters.

But the position of data may also matter:

- what it is near,
- what comes before it,
- what comes after it,
- what it is contrasted against,
- what boundary it marks,
- what role it belongs to,
- and what future reasoning it prepares.

If true, then better models may not require only larger datasets or larger architectures.

They may also require better curriculum geometry.

Not just more bricks.

Better rooms, roads, walls, doors, and limbs.