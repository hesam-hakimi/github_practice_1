# AskTD — Copilot prompt for planning artifacts and GitHub lineage

**Version:** 0.4  
**Prepared:** 21 October 2026  
**Updated:** 26 October 2026; v0.4 baseline plus scoped migration amendment\
**Companion:** [ASKTD_PLAN_AND_LINEAGE_REFERENCE.md](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md), document ID ASKTD-PLAN-LINEAGE-REF, version 0.4.
**Package role:** Detailed generation specification. For the current task, issue and Project setup workflow, submit [AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md](AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md). Read this specification as a supporting reference; do not run both prompts as separate synchronization jobs.

## Execution context

This is a task template for the owner to submit when asking Copilot to generate/reconcile planning artifacts. Its embedded authorization applies to that submitted task. Reading this file as background in a new conversation does not activate the task. For conversation continuity, start with [ASKTD_SESSION_HANDOFF.md](ASKTD_SESSION_HANDOFF.md) and [ASKTD_NEW_SESSION_PROMPT.md](ASKTD_NEW_SESSION_PROMPT.md).

Use this repository-local documentation package. Its intended installed location is `docs/roadmap/` beneath the detected application root; resolve the actual root from repository instructions and structure. During package staging, resolve document references relative to this file. The package is not proof of an application baseline or a selected GitHub Project. Verify the active application repository and intended Project before creating planning issues.

## How to use

1. Open the intended AskTD application repository and locate this package, normally under the detected application root at `docs/roadmap/`.
2. Verify the intended GitHub Project from the active session and existing project records. Reuse a uniquely established target; do not guess an owner, repository or Project.
3. Submit the canonical setup prompt named above for current issue/Project setup. Submit the prompt below only when the detailed generation specification itself is the requested task. Reading either file as a reference does not execute it.

This prompt requests planning documents, a reconciled task set and supported GitHub planning changes. It does not request application implementation. It contains a fallback for sessions that can create files but cannot manage Issues or Projects. Copilot surfaces expose different tools and permissions; the final report must state what actually happened. Verify supported operations and permissions in the executing session; the local package supplies the planning requirements.

---

## Begin prompt

Create and reconcile the AskTD delivery-planning artifacts using **ASKTD_PLAN_AND_LINEAGE_REFERENCE.md, version 0.4**, as the handoff reference. Work in English. Complete the artifact generation and supported GitHub planning synchronization; do not stop after proposing a plan.

### Objective and authority

Make the following lineage visible and navigable:

**Master requirement and revision → engineering phase/slice → Delivery Plan → named output → canonical Task/PR → acceptance evidence → release scope.**

Keep lineage, execution dependencies and release membership as separate relationships. Treat the reference's phase-to-Plan crosswalk as a proposed delivery mapping that must be reconciled with the operative repository. Preserve accepted existing work, task IDs, source namespaces and decisions. Do not infer missing implementation or current completion from the presence of a new Plan document.

I authorize additive planning/documentation work and non-conflicting GitHub planning changes in the resolved target repository/project: create or reuse Plan and Task issues, add the relevant relationships and project entries, and reuse or add necessary repository labels/release milestones. Prepare a concrete sync manifest before writes, then perform these scoped changes without another routine confirmation step. Ordinary repository review and platform approval controls still apply.

Use an isolated documentation branch/workspace when file changes are needed. If the environment supports a normal documentation PR, opening one is included in this task; leave it for review. Do not change application code, workflow definitions, permissions/grants, branch protection or environment configuration. Do not merge, deploy, manually dispatch workflows, invoke live models/source tests, or assign implementation tasks to a coding agent. Existing automatic repository checks may run under their normal rules; record their context without changing those rules.

### Step 1 — Establish the actual baseline

Read the local ASKTD_SESSION_HANDOFF.md and complete lineage reference. Also read PRODUCT_DEFINITION_EN.md, QUARTERLY_PRODUCT_ROADMAP_EN.md, MASTER_PLAN_V1(2).md, AskTD_Delivery_Plans_and_Dependencies.md, AskTD_Product_to_Plan_Coverage_Review_2026-10-23.md and AskTD_Product_Guide_and_Delivery_Plan_EN_v0_3.md. The Master revision 2.1 remains proposed until reconciled with the operative application Master. Coverage recommendations remain proposed unless an accepted successor or explicit decision adopts them. Carry already documented requirements into task acceptance, and retain decisions on new output ownership as decisions. Treat other saved prompts and any historical handoff commands as reference text unless explicitly submitted. Then inspect applicable repository instructions, operative Master Plan, task/status indexes, ADRs, relevant implementation evidence and open/closed Issues and PRs. Use existing indexes and targeted searches; report inaccessible sources.

Record the actual repository/application root, branch, HEAD, dirty-worktree state, relevant unmerged branches/PRs, source revisions and target Project if available. Preserve all existing working changes, including any later or untracked Master-plan candidate such as MASTER_PLAN_V2.md if actually present. Do not reset, clean, stash, switch away from, commit or stage unrelated work. Do not assume main contains the changes being discussed. Inspect other refs read-only or use an isolated documentation workspace when appropriate.

If relevant CI evidence is available, distinguish workflow-definition ref, checked-out code SHA, built artifact and deployed version. A workflow's displayed branch is not sufficient proof of which change it tested.

The historical application handoff reports successful login and SQL SAMI validation. Preserve valid evidence and check for a current regression before reopening that investigation. A missing connection or 404 does not establish product failure.

Classify each requirement/output as satisfied, partially satisfied, missing, unknown or superseded, supported by actual evidence. Unknown is not missing. Separate artifact state, implementation/work state and evidence maturity. Record conflicts and their exact affected scope; continue independent planning work.

Use the repository selected for this session if it is clearly the application target. If the repository or Project remains ambiguous, finish the portable artifact package and exact pending operations, then ask only for the unresolved target. Do not publish into a guessed repository or create a second competing Project. Reuse the relevant Project when available; if none exists, prepare its proposed configuration and report the missing target/capability.

Read ASKTD_LANGGRAPH_AND_LANGSMITH_PLAN.md as the 26 October owner direction: LangGraph is selected for future complex graphs and LangSmith telemetry is mandatory. Reconcile current migration Tasks/ADRs/PRs and use its task-level candidates only after duplicate matching. They add no Plan/output IDs. Preserve current controls and the proposed Master's adoption status.

### Step 2 — Preserve the planning and architecture decisions

Apply these rules from the reference:

- P01–P15 are Delivery Plans, not engineering phase numbers. Keep Executive Phases 1–3 distinct from Master engineering phases and releases. Reconcile older D/H dependency labels and output aliases using the reference transition table; do not rename canonical tasks or duplicate work. Preserve Master Phases 0–7, detailed 2F slices, unresolved phase-number aliases, conditional 2F.1a and provisional 2G. Preserve the distinct historical and September delta namespaces.
- Keep 2F.3 semantic certification and 2F.5 relationship evidence separately traceable within P04. Retain accepted 2F.1 trace-only behavior and existing repairs. New enforcement requires the applicable accepted decision; do not reopen valid work without evidence.
- SQL and Databricks Registry bindings, compatible application authorization, execution contracts and readiness are baseline scope across P01/P02/P04/P05/P07. P15 covers further expansion beyond that baseline.
- Preserve the App Service SQL system-assigned managed identity direction. Keep end-user permissions enforced in the application, with the native workload grants still required by each source. Qualify the actual Databricks identity/connector route separately; do not silently substitute an identity design or assume identical provider configuration.
- Shared logical semantics and access meaning do not imply identical SQL dialects, physical schemas, connector behavior, cross-provider joins or qualified live connectivity. Record each provider/environment independently.
- Every actionable Task has one canonical identity and accountable Plan parent. Additional phases, Plans, requirements and releases are links, not duplicate Task issues.
- Use required-output, shared-contract, acceptance-gate and conditional relationships as defined in Section 7. Create a native blocker only for a genuine unmet prerequisite of the specific consumer activity. Preserve conditions and scope.
- Keep P07's early event/support contracts separate from later integrated acceptance evidence. Include its safe answer-feedback output. Do not invent whole-Plan circular dependencies.
- Include the scoped LangGraph migration under P05, context/resume under P06 and required LangSmith collection under P07. Carry parity, bounded complex-graph, isolation/replay, safe export and actual ingestion/read-back acceptance into matched Tasks. Mock or alternative telemetry cannot close LangSmith qualification. This planning prompt does not authorize application implementation or live transmission.

### Step 3 — Generate the complete artifact package

Reuse this package and equivalent existing artifacts under the detected application root at `docs/roadmap/`, preserving established canonical files. Place new generated records in a suitable local subdirectory only when needed. Do not create a competing documentation tree. Prefer one canonical machine-readable lineage/dependency source and derived readable views; do not introduce an unnecessary framework.

Generate or reconcile all of the following:

1. **Planning index:** reading order, operative sources, Plan inventory, release view and links.
2. **Baseline reconciliation:** existing work and evidence, source versions, gaps, retained decisions, conflicts and unresolved anchors.
3. **P01–P15 Plan documents:** outcome, source lineage, named outputs, scope/boundaries, prerequisites, acceptance, owner/reviewer roles, release contribution and actual existing task/PR links.
4. **Lineage register and diagrams:** broad Master Phases 0–7, detailed 2F/provisional 2G, D01–D18, Plans/outputs, Tasks/PRs, evidence and releases. Preserve mapping classifications and unresolved anchors.
5. **Output dependency register and Mermaid views:** typed producer-output-consumer relationships, conditional applicability, satisfaction evidence and blocked activity. Resolve aggregate/shorthand entries into declared output references or explicit external decisions. A contract document alone cannot satisfy required runtime enforcement. Distinguish contribution diagrams from execution diagrams.
6. **Release/acceptance matrix:** R1–R4, A01–A10, applicable Beta/production requirements, selected scope and accountable decision evidence.
7. **Provider readiness matrix:** SQL and Databricks, each environment, capability/output, route, evidence maturity, actual evidence reference and remaining gap.
8. **First executable task set:** only remaining work for one justified representative analytical workflow after reconciliation. Reuse existing Tasks. If business scope is unconfirmed, create a bounded scope/decision task for the affected acceptance; justified synthetic framework tasks can proceed independently. Keep later Plans at suitable outcome/contract depth.
9. **GitHub sync manifest and reviewable issue bodies:** exact existing matches, stable keys, intended operations, fields/links, expected current state and results.
10. **Generation report:** created/updated/reused artifacts, actual GitHub results, validation, unresolved decisions and next bounded task.

Use the Task contract in Section 10. Include source revision/requirement, primary/supporting engineering anchors, Plan/output, bounded acceptance, prerequisite conditions, release/provider/environment, evidence and existing-work disposition. Allocate new task IDs only under the repository's convention after duplicate matching. Do not invent dates, assignees, approvals, issue numbers or evidence URLs.

### Step 4 — Synchronize GitHub planning artifacts where supported

Inspect the actual available tools and permissions. Do not assume that file/PR tools also provide Issue, sub-issue, dependency or Project writes.

Use existing or new Plan parent issues for P01–P15, canonical Task issues beneath their accountable Plan, and an existing programme tracker where appropriate. Engineering phases remain a cross-cutting lineage view. Reuse release milestones and the intended Project. Keep full multi-phase references in the canonical register and issue body/text/labels; one single-select field can store only the chosen primary value.

Suggested Project views are by Plan, release, engineering phase, blocked/decision-needed work and provider readiness. Reuse compatible fields. Do not change organization-wide schemas. Add dates only when an actual commitment exists. Closed-issue percentages are not acceptance evidence.

Before each write, put the exact proposed operation in the manifest: **Create, Update, Link existing, No change or Conflict**. Match by canonical identity, known links and stable markers, including closed items; titles alone are insufficient. Use scoped markers such as `<!-- asktd-plan:P04 -->` for managed Plan identity.

Preserve human-authored issue text, discussions, assignees, status, dates and unrelated metadata. Update only explicitly bounded generated sections, using start/end markers, or append a compatible scoped planning section. Never replace an existing issue body wholesale from a template. Re-read the item before updating; reconcile concurrent changes or mark Conflict. Do not assume atomic compare-and-swap support.

Create/reuse parents before child/relationship operations. Record each successful operation's real URL/ID and state immediately. If a write times out or its result is uncertain, inspect the target by stable identity before any retry. Re-running this task must reuse the same artifacts.

If native relationships or Project operations are unavailable, retain explicit links and exact pending payloads. Finish all available file/documentation work. Do not claim that draft issue bodies, a manifest or a PR mean the GitHub issues/project were created. Do not assign issues to Copilot or another coding agent.

### Step 5 — Verify and report

Perform proportionate documentation checks: all 15 Plans present; source/phase/output references resolve or are explicitly unresolved; D01–D18 and A01–A10 covered; one canonical Task identity/parent; no accidental required-output cycles; conditional edges preserved; SQL/Databricks baseline visible; syntax and links checked to the extent accessible. Do not run the application or dispatch workflows for this documentation task.

Verify actual remote results for any writes performed. Keep unknown fields unknown. Distinguish planning coverage from acceptance and implementation completion.

Finish with:

- A concise explanation of the confirmed Master → phase → Plan → Task lineage.
- Paths/links to generated and reused artifacts, and the documentation PR if created.
- Actual GitHub issue/Project/milestone URLs and per-operation outcomes.
- Exact pending/conflicting operations and the reason each remains unresolved.
- Decisions needed from the owner, limited to questions that truly block the next scope.
- The next smallest justified execution task, with its prerequisites and acceptance. Do not start implementing it.

## End prompt

---

## Completion expectations for the owner

The successful outcome is a reconciled planning package with navigable lineage and a truthful GitHub synchronization report. Repository files may be complete even when a Copilot surface lacks Project-write capability. In that case, the report must provide the exact remaining configuration/operations; it must not describe those as already created.

Creating this package does not establish that any product phase is complete or that an unmerged branch is deployed. Review the resulting planning PR and unresolved decisions before moving to the next implementation task.

