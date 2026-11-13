---
title: BPMN Trainer and Simulator
tags:
date: 2026-11-13
toc: true
toc_sticky: true
---

# From BPMN diagrams to process experiments: a university trainer

- Audience: university lecturers, programme leaders, and teaching-lab coordinators

## Blog: "Our process looks right. Why are students still waiting?"

Imagine a seminar in business informatics. A lecturer asks students to model a familiar university process: a student submits an application, an administrator checks it, and an academic reviewer makes a decision.

The diagrams look convincing. There are tasks, lanes, gateways, and an end event. But the lecturer asks a different question:

**"What happens when one hundred applications arrive and only one person can check them?"**

A static diagram cannot answer that question on its own. This is where **bpmnsim can become a BPMN trainer**: students can draw a process, follow its control flow, configure a workload, and investigate the consequences of their assumptions in the same browser application.

The following classroom story is a proposed teaching use case, not a report of an actual university deployment. Its educational benefits are hypotheses for a pilot to evaluate.

### First, make the diagram explain itself

Working in small groups, students build a simplified application process with one start event:

1. Receive the application.
2. Check the documents in an administration lane.
3. At an exclusive gateway, select either a complete-application route or an additional clarification task.
4. Review the application in an academic-review lane.
5. Notify the student and finish.

Before assigning durations or costs, the groups use deterministic replay. They advance the tokens, stop at the exclusive gateway, and explain their branch choice. A separate, small parallel split/join example lets the lecturer demonstrate why a join must wait for both incoming paths.

The exercise changes the conversation from "Does this symbol look correct?" to "What does this structure actually do?"

Students can also animate a representative case through the integrated token simulation. The lecturer distinguishes that animation from replay: the case-player's **Schritt** control pauses or resumes an animation; it is not the same discrete step operation as the replay toolbar.

### Next, turn assumptions into an experiment

The lecturer introduces a fictional configuration:

| Parameter | Baseline teaching assumption |
| --- | --- |
| Workload | 100 applications |
| Arrival interval | One application every 10 minutes |
| Document check | 25 minutes |
| Clarification route | Relative branch weight 20; complete route weight 80 |
| Clarification task | 10 minutes |
| Academic review | 10 minutes |
| Administration | 1 resource, 40 total working hours per week |
| Academic review | 2 resources, 80 total working hours per week |
| Resource cost | EUR 30/hour for administration; EUR 50/hour for review |

These are exercise inputs, not measured university data or simulation results. Other task durations and fixed execution costs must be specified explicitly before the experiment.

An important teaching detail: weekly hours are **the total for the role**, not hours per person. Two people working 40 hours each require an entry of 80 hours. The simulator distributes that capacity across the resources and Monday-to-Friday working windows.

The groups enter durations, costs, arrival frequency, branch weights, and lane-based resource settings. They run the multi-case simulation and inspect completed versus started cases, cost, average cycle time, resource consumption, and bottleneck markings. The spreadsheet export adds role utilization, maximum queue length, and total waiting time.

Now the lecturer asks students to separate three ideas:

- **Processing time:** the work an application requires.
- **Waiting time:** the delay before a busy role can begin that work.
- **Cycle time:** the elapsed time from arrival to completion, including applicable waits and non-working periods.

They must also distinguish summed cycle time across cases from the experiment's elapsed horizon, or makespan. A large total does not mean that every student waits that long.

### Then, challenge the obvious solution

Each group tests a different intervention:

- **Capacity:** increase administration from one resource and 40 weekly hours to two resources and 80 weekly hours.
- **Process redesign:** reduce the document-check task from 25 to 15 minutes.
- **Demand smoothing:** increase the interval between arrivals.
- **A controlled contrast:** increase resource count while holding total weekly hours constant.

That last experiment is particularly useful. Adding a second resource without adding weekly hours is not equivalent to doubling capacity. Students have to defend the configuration, not just click "more resources."

Scenario tabs keep alternatives organized. The results sidebar compares the current and previous run within the selected scenario; it is not an automatic cross-scenario comparison matrix. Groups export their reports and assemble a comparison table for their assignment.

There is no promised winner. A queue may shrink, a bottleneck may move, or extra capacity may change delay without changing the modeled hourly work cost as students expected. The discussion is about what the model includes, what it excludes, and whether the recommendation follows from the evidence.

### Finally, present an argument rather than a screenshot

Each group submits:

- A saved BPMN diagram.
- A table of scenario assumptions, including branch weights and total weekly role capacity.
- Exported results for the baseline and alternatives.
- A short recommendation explaining cost, delay, and workload trade-offs.
- A limitations paragraph covering simplified calendars, random branch choices, and missing real-world factors.

The lecturer assesses model semantics, experimental design, interpretation, and critical reflection. A polished diagram alone is no longer enough.

The learning opportunity is straightforward: **model, predict, simulate, compare, explain**.

## Why this is attractive for university teaching

| Advantage | Academic use |
| --- | --- |
| Browser-based editor and simulator | Students can work with one interface instead of switching between a drawing tool and a separate simulation environment. |
| Visible control-flow replay | Lecturers can discuss exclusive choices and parallel synchronization before introducing quantitative analysis. |
| Workload and lane-based resources | Exercises connect BPMN to queues, capacity, calendars, and operational trade-offs. |
| Costs and durations | Students must make assumptions explicit and evaluate more than visual correctness. |
| Scenarios and run history | Groups can organize alternatives and revisit locally stored reports. |
| BPMN files and spreadsheet reports | Models and results can support seminar submissions and classroom discussion. |
| Static-web deployment architecture | A teaching pilot need not provision an application backend; hosting and logging still require institutional review. |
| Inspectable TypeScript source and existing tests | Computing courses can examine the simulation implementation and compare it with the model's intended semantics. |

Suitable contexts include business process management, business informatics, information systems, operations management, and software-engineering labs. Advanced students could use the repository's seeded workload tests to explore reproducibility and sensitivity analysis.

These are potential advantages, not evidence of improved grades, reduced teaching costs, or proven learning gains. Verify licensing and institutional requirements before adopting or redistributing the application.

## A practical 90-minute pilot

| Time | Activity | Evidence of learning |
| --- | --- | --- |
| 0-10 min | Introduce the application process and define scope | Groups state what the model excludes. |
| 10-30 min | Model and replay the process; discuss a parallel example | Students explain branch choices and synchronization. |
| 30-45 min | Configure and run a baseline | A written parameter table accompanies the results. |
| 45-65 min | Test capacity, redesign, or arrival alternatives | Each group identifies the variable it changed. |
| 65-80 min | Export and compare findings | Recommendations distinguish work, waiting, cost, and cycle time. |
| 80-90 min | Present limitations and conclusions | Students justify a recommendation and name a counterexample. |

For assessment, one possible rubric allocates 30% to model semantics, 25% to configuration and experimental control, 30% to interpretation, and 15% to limitations and reproducibility. This is a proposed rubric, not a built-in grading feature.

Pilot success criteria should be observable: each group can explain an exclusive choice and a parallel join, document a baseline and at least two alternatives, and support its recommendation with exported results. The lecturer should record setup difficulties and assess explanations rather than assume animation alone improves understanding.

## The pitch

### Thirty-second pitch

**Bring a process laboratory into your BPMN seminar.** With bpmnsim, students do not stop at drawing a workflow: they replay its logic, introduce workload and limited resources, and compare the resulting time and cost trade-offs. A browser-based editor, scenario settings, and exportable reports make a small teaching pilot practical. Start with one familiar university process and ask students to defend an improvement with evidence, not just a better-looking diagram.

### For a programme leader

The proposal is not to replace an enterprise process platform. It is to add a focused teaching instrument between BPMN notation and quantitative process analysis. One application can support introductory demonstrations, group experiments, and implementation-focused computing assignments.

**Recommended next step:** approve one seminar pilot with synthetic data, institution-approved hosting and logging settings, and a simple learning-outcome rubric. Expand only after evaluating usability, model limitations, and student explanations.

## Adoption conditions and honest boundaries

- **Local storage is not a privacy guarantee.** The application currently stores data locally, but remote Loki logging is enabled unless configured otherwise. Autosave logs can include full diagram XML. For a pilot, build with `VITE_LOKI_ENABLED=false` and use synthetic data; that setting disables remote log pushes but leaves console logging. Do not describe the default build as fully offline or as keeping all information on the device. See [logger configuration](../src/util/logger.ts) and [autosave logging](../src/main.ts).
- **Persistence has changed since the early chats.** Historical sessions describe SQLite/WASM. The current [browser store](../src/db/store.ts) uses the [in-memory JSON store](../src/db/memStore.ts), persisted as bytes in IndexedDB. Clearing browser storage can remove saved work. Download diagrams and export reports; neither export should be represented as a complete backup of all scenario settings and history.
- **The simulator is a simplified teaching model, not full BPMN execution.** The [graph adapter](../src/model/graph.ts) treats inclusive, event-based, and complex gateways as exclusive choices, and subprocesses/call activities as tasks. Message flows are not wired into the simulation graph. Use a single-start process with tasks and XOR/AND gateways for the introductory quantitative exercise.
- **Multi-start collaboration metrics need caution.** The historical workload session explicitly notes shared case bookkeeping across two starts. Its request/response fixture demonstrates workload execution, not validated end-to-end message synchronization or authoritative collaboration cycle times.
- **Calendars and arrivals are simplified.** Role calendars use Monday-to-Friday working windows; arrivals use a fixed interval rather than a full demand calendar. Tasks without configured role pools are unconstrained. Use positive resource counts and weekly hours when teaching queues.
- **UI and engine capabilities differ.** The engine supports fixed, exponential, and uniform durations, but the current duration drawer writes fixed durations. UI runs select a fresh random seed. Seeded experiments and the 100-level workload sweep exist in tests, not as a built-in experiment-management screen.
- **Reports are not a statistical study.** Random branch choices can vary between runs. Repeat experiments and disclose assumptions; confidence intervals and automated statistical analysis are not advertised as built-in features.
- **Exports and comparisons are lightweight.** The `.xls` export is an Excel-openable HTML table, not a native `.xlsx` workbook. The sidebar shows current versus previous runs, with additional comparison left to the assignment workflow.
- **Institutional features are not established here.** LMS integration, automated grading, shared real-time editing, accessibility certification, and enterprise simulation equivalence were not verified. Evaluate these needs separately.

## Session record and evidence

### Request and scope

User request:

> read all chat sessions and write session in /doc/yyyy-mm-dd-hhmmss-topic.md . write blog usecase story for (ths) bpmn trainer for academic  usage in university pros pitch .

Interpretation: "this BPMN trainer" refers to bpmnsim; `/doc/` refers to this repository's documentation folder. This document combines a session synthesis, a proposed classroom story, academic advantages, and a pitch in English.

All nine saved topic/session chat logs found in [chatlog](./chatlog/) were read, together with all four stored turns of the additional accessible historical workload session. Session discovery included archived sessions for this workspace. The current conversation was also considered. Some saved logs overlap and summarize assistant turns; they are not nine independent verbatim transcripts.

The cloud history queries returned no matching sessions. Local history and workspace session discovery exposed the workload session and this current conversation. This record therefore covers **all repository chat material found through those sources**, not a claim to have read unavailable, deleted, unrelated, or private conversations elsewhere.

### Historical synthesis

| Source | Contribution to the trainer story |
| --- | --- |
| [2026-07-20: editor and simulator](./chatlog/2026-07-20-bpmn-editor-simulator.md) | Established the backend-free web editor, local BPMN files, deterministic replay, interactive XOR choices, AND split/join behavior, and integrated token simulation. |
| [2026-07-20: GitHub Pages build](./chatlog/2026-07-20-github-pages-build.md) | Documented relative asset paths and static deployment preparation; not evidence that a live site was checked in this session. |
| [2026-07-20: stochastic DES and SQLite](./chatlog/2026-07-20-stochastic-des-sqlite.md) | Introduced duration distributions, weighted branches, seeded simulation, and historical SQLite/IndexedDB persistence. |
| [2026-07-20: resource simulation view](./chatlog/2026-07-20-resource-simulation-view.md) | Added lane-based resources, queues, working calendars, cost reporting, scenarios, overlays, and spreadsheet export. |
| [2026-07-20: combined simulation session](./chatlog/2026-07-20-simulation-session.md) | Preserved the decisions behind DES and resource simulation; overlaps the two preceding topic logs. |
| [2026-07-23: editor and playback fixes](./chatlog/2026-07-23-editor-fixes-token-simulation-resize.md) | Recorded graph-refresh fixes, Save-As with download fallback, task resizing, and native token-simulation case playback. |
| [2026-07-23: logging and Loki](./chatlog/2026-07-23-logging-loki.md) | Established direct browser log shipping, making deployment configuration relevant to academic data handling. |
| [2026-07-23: full XML logging and large diagrams](./chatlog/2026-07-23-log-diagram-xml-big-diagram-e2e.md) | Recorded full diagram XML logging and a 200-task logging test; this is not a general scalability benchmark. |
| [2026-07-23: replay-token visibility](./chatlog/2026-07-23-red-replay-token-mode-visibility.md) | Clarified the difference between replay tokens, native animation, and stochastic-result badges. |
| Additional session: stochastic simulation workload addition, 2026-07-23 | Recorded a seeded sweep across 100 workload levels, a UI run of 100 cases, printed statistics, and the multi-start cycle-time caveat. |

The additional workload session distinguished **100 separate simulations at workload levels 1-100** from **one UI simulation containing 100 cases**. The sweep used stochastic durations and per-task costs; the UI exercise used fixed durations and no configured costs or resources. Those results must not be combined into one claimed benchmark or reused as results for the fictional university exercise.

### What this session did

1. Read the repository guidelines, project README, and every saved chat log.
2. Searched accessible repository session history and read the additional workload conversation.
3. Checked relevant implementation and test evidence to resolve differences between historical descriptions and current capabilities.
4. Wrote this combined session record and university-use-case article without changing application code.

Key current evidence:

- [Project overview and setup](../readme.md).
- [Simulation parameters and report definitions](../src/sim/desTypes.ts).
- [Resource-constrained simulation](../src/sim/simulation.ts).
- [Configuration drawer](../src/ui/simConfig.ts) and [results sidebar](../src/ui/simSidebar.ts).
- [Scenario controls](../src/ui/scenarioTabs.ts), [case animation](../src/ui/casePlayer.ts), and [spreadsheet export](../src/ui/excel.ts).
- [Resource-view, persistence, and export E2E cases](../e2e/simulation-view.spec.ts).
- [Calendar, queue, cost, and branch-weight unit cases](../test/simulation.test.ts).
- [Seeded 100-level workload experiment](../test/workload-sweep.test.ts) and [100-case UI exercise](../e2e/workload-100.spec.ts).

Historical logs report passing tests at their respective dates. Tests were read as evidence of intended coverage, not rerun for this documentation-only task. No new classroom simulation was executed, no live deployment was verified, and no learning-effectiveness claim was measured.
