EXPERIMENT_001.md

Experiment 001: Structured Curriculum vs Random Data Order

Purpose

This experiment tests whether a small LLM trained or fine-tuned on structured curriculum data performs better than a comparable model trained on the same content in random order.

The goal is not to prove the full Relational Curriculum Geometry Hypothesis.

The goal is to test one narrow claim:

«Data order and relational structure may affect learning efficiency, transfer, boundary handling, uncertainty surfacing, and multithread reasoning.»

---

Core Question

Given the same source examples and the same token budget, does a model trained on staged relational curriculum data outperform a model trained on randomly ordered data?

---

Narrow Domain

Use one controlled domain for the first experiment.

Recommended first domain:

«Basic programming and debugging»

This domain is useful because it allows clear tests for:

- recall,
- rule use,
- near transfer,
- boundary cases,
- uncertainty,
- tool-use discipline,
- role separation,
- and multithread reasoning.

---

Model Groups

Train or fine-tune several comparable small models.

All groups should use:

- same base architecture,
- same model size,
- same training budget,
- same token count,
- same source examples,
- same evaluation set,
- and same training settings where possible.

---

Group A: Random Baseline

The dataset is cleaned but randomly ordered.

This tests ordinary bulk exposure.

---

Group B: Domain Grouped Baseline

The dataset is grouped by broad topic.

Example groups:

- syntax,
- variables,
- functions,
- errors,
- tests,
- debugging,
- file operations,
- tool-use examples.

This tests whether simple grouping helps.

---

Group C: Complexity Curriculum

The dataset is grouped by topic and ordered from basic to complex.

Example order:

1. primitive concept,
2. simple example,
3. ordinary use,
4. common error,
5. debugging example,
6. near-transfer example,
7. boundary case.

This tests whether staged complexity helps.

---

Group D: Full Relational Curriculum

The dataset is grouped by topic, ordered by complexity, and explicitly arranged around relation types.

Example relation tags or folders:

- prerequisite,
- ordinary case,
- exception,
- contrast,
- analogy,
- boundary case,
- insufficient information,
- unsafe action,
- requires verification,
- user role,
- assistant role,
- host role,
- tool role,
- reviewer role,
- multithread task.

This tests the fuller hypothesis.

---

Dataset Design

The dataset should contain the same base examples for all groups.

Only the ordering and structural presentation should change.

Example curriculum path:

1. What a variable is.
2. What assignment means.
3. What a function is.
4. What a return value is.
5. What an error message is.
6. How to read a simple stack trace.
7. How to identify a syntax error.
8. How to identify a type error.
9. How to identify a logic error.
10. How to distinguish symptom from cause.
11. How to propose a safe fix.
12. How to ask for missing information.
13. How to avoid pretending certainty.
14. How to separate user intent from code truth.
15. How to separate assistant suggestion from host action.
16. How to handle a tool result that contradicts the initial guess.
17. How to combine user goal, error log, test output, and permission boundary.

---

Evaluation Tasks

The evaluation should measure more than simple correctness.

It should test the exact behaviours the hypothesis predicts.

---

1. Recall

Can the model answer simple questions from the training domain?

Example:

«What is a return value?»

---

2. Rule Use

Can the model apply a basic rule directly?

Example:

«This function does not return anything. What is likely wrong?»

---

3. Near Transfer

Can the model apply the same concept to a slightly different case?

Example:

«The training examples used Python functions. The test uses JavaScript functions. Can the model identify the same missing-return pattern?»

---

4. Cross-Representation Transfer

Can the model move between formats?

Example inputs:

- prose description,
- code snippet,
- table of test results,
- error log,
- structured JSON.

The model should identify the same underlying issue across formats.

---

5. Boundary Detection

Can the model tell when an example almost fits a known category but does not?

Example:

«This looks like a syntax error, but the code runs. The actual problem is a logic error. What evidence separates the two?»

---

6. Uncertainty Surfacing

Does the model say when it lacks enough information?

Example:

«The app crashes sometimes. What is the bug?»

A good answer should avoid inventing certainty and should ask for logs, reproduction steps, environment details, or recent changes.

---

7. Role Discipline

Can the model distinguish between roles?

Example:

«The user wants the bug fixed. The assistant can suggest a patch. The host controls file writing. The test runner verifies the result. What should happen next?»

A good answer should not pretend the assistant owns all authority.

---

8. Tool-Use Discipline

Can the model tell when tool use is required, optional, or inappropriate?

Example:

«The user asks for a code patch but has not provided the file. Should the model invent a patch, ask for the file, or claim it edited the file?»

---

9. Multithread Reasoning

Can the model hold several constraints at once?

Example:

«A user asks for a fix.
The error log suggests a missing file.
The README says the file is generated automatically.
The host environment is read-only.
The previous attempt failed because the assistant edited the wrong folder.
What is the safest next action?»

A strong answer should account for all threads.

---

10. Failure Legibility

When the model fails, can the failure be classified?

Possible failure types:

- missing prerequisite,
- weak transfer,
- boundary confusion,
- uncertainty failure,
- role collapse,
- tool misuse,
- ignored constraint,
- overconfident invention,
- multithread collapse.

The structured model should ideally produce more diagnosable failures.

---

Metrics

Use both quantitative and qualitative scoring.

Possible metrics:

Accuracy

Did the model answer correctly?

Transfer Score

Did the model apply the concept to a new surface form?

Boundary Score

Did the model avoid forcing an almost-fit example into the wrong category?

Uncertainty Score

Did the model surface missing information or weak evidence?

Role Discipline Score

Did the model preserve distinctions between user, assistant, host, tool, and reviewer?

Tool Discipline Score

Did the model use, refuse, or request tools appropriately?

Multithread Score

How many active constraints did the model preserve?

Prompt Burden

How much prompt scaffolding was required to get a good answer?

Lower prompt burden may indicate cleaner internal structure.

---

Expected Result If Hypothesis Is Supported

The full relational curriculum model should show:

- better transfer,
- better boundary handling,
- better uncertainty surfacing,
- better role discipline,
- better multithread reasoning,
- fewer overconfident guesses,
- and lower prompt scaffolding requirements.

The complexity curriculum model may outperform the random baseline even without full relation labels.

The domain grouped baseline may show some improvement, but less than the full curriculum model.

---

Expected Result If Hypothesis Is Not Supported

The random baseline performs similarly to the structured models once token count and data quality are controlled.

Any apparent gains are explained by:

- cleaner examples,
- duplicate exposure,
- label leakage,
- benchmark contamination,
- better formatting,
- or more examples of the tested task type.

If this happens, the hypothesis should be narrowed or revised.

---

Important Controls

To make the test meaningful, control:

- total tokens,
- example count,
- model size,
- training settings,
- source material,
- evaluation contamination,
- duplicate examples,
- formatting differences,
- and label leakage.

The structured curriculum should not secretly contain more information than the baseline.

It should contain the same information in a different order and structure.

---

Useful Ablations

A. Shuffle Test

Take the full relational curriculum and randomly shuffle it.

If performance drops, order may matter.

---

B. Remove Labels

Keep the same staged order but remove relation labels.

If performance drops, explicit relation labels may matter.

---

C. Remove Boundary Cases

Keep ordinary examples but remove edge cases.

If boundary handling drops, boundary examples matter.

---

D. Remove Role Examples

Remove user/assistant/host/tool/reviewer role examples.

If role discipline drops, role curriculum matters.

---

E. Remove Uncertainty Examples

Remove insufficient-evidence and ambiguous cases.

If uncertainty surfacing drops, uncertainty curriculum matters.

---

Minimal Dataset Shape

A tiny first version could use:

- 50 primitive examples,
- 50 simple use examples,
- 50 common error examples,
- 50 debugging examples,
- 50 near-transfer examples,
- 50 boundary examples,
- 50 uncertainty examples,
- 50 role/tool examples,
- 50 multithread examples.

Total: 450 examples.

This is not enough to build a strong model, but it may be enough to test whether structure creates directional improvement.

---

Experiment Loop

1. Build source example pool.
2. Create random baseline dataset.
3. Create domain grouped dataset.
4. Create complexity curriculum dataset.
5. Create full relational curriculum dataset.
6. Train or fine-tune comparable small models.
7. Run evaluation battery.
8. Classify failures.
9. Compare results.
10. Feed failure patterns back into the sorter.
11. Improve curriculum structure.
12. Repeat.

---

Success Criteria

Experiment 001 is successful if it produces interpretable evidence either for or against the hypothesis.

A positive result would show that structured curriculum improves targeted behaviours under controlled conditions.

A negative result would still be useful if it shows that ordering, grouping, or relation labels did not matter under this setup.

The goal is not to win the argument.

The goal is to make the argument testable.

---

Working Summary

Experiment 001 tests whether small models learn differently when given the same data in different relational structures.

The central question:

«Does curriculum geometry change model behaviour?»

If yes, then the dataset sorter is not just preprocessing infrastructure.

It is a possible model-shaping instrument.

If no, then the hypothesis needs revision.

Either outcome improves the build path.