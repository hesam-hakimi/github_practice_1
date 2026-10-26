# AskTD — Copilot task, issue and Project setup prompt

Prepared: 23 October 2026 (UTC)
Amended: 26 October 2026 (America/Toronto), scoped LangGraph/LangSmith planning direction.\
Purpose: turn the reconciled delivery plan into assignable GitHub work and maintainable project visibility. This is the canonical execution prompt for planning synchronization in this package. Reading it does not execute it.

## How to use

1. Open the intended application repository in a Copilot session with repository context. Agent mode with authorized GitHub tools or authenticated GitHub CLI is suitable. Available operations depend on the actual surface, version and permissions.
2. Locate this repository-local package, normally at `docs/roadmap/` beneath the detected application root. Read the maintained Master, portfolio, product documents, guide and coverage review from that directory. During staging, resolve all document references relative to this file. No external document or chat attachment is required to understand the planning package.
3. Verify the intended existing GitHub Project and application repository from the active session and existing records. If the target is ambiguous, request only its exact identifier. A verified team roster is optional; without it, tasks remain role-owned and unassigned.
4. Submit the prompt below. Its authorization permits additive planning synchronization, not application implementation. It requires a reviewable operation manifest before writes but does not add a routine approval stop. GitHub's own draft review, tool approval and repository controls still apply.
5. If you want a preview only, explicitly add: **“PREVIEW ONLY: prepare the full package and sync manifest; do not write to GitHub.”** This overrides the synchronization authority below.

## Begin prompt

Act as the AskTD delivery planner and GitHub project coordinator. Work in English. Convert the reconciled product and delivery plans into a practical, dependency-aware task backlog and GitHub Project. Complete supported planning operations and verify their actual results.

### 1. Targets, scope and authority

Documentation package: the directory containing this file, intended to be installed at `docs/roadmap/` beneath the detected application root. Resolve the actual application root from repository instructions and source structure, and record the active repository, branch and HEAD. A staged package directory is not proof that application source is present.

Application repository: use the exact repository established by the active session and existing records; otherwise ask for its identifier. Do not infer the application issue target from the package location alone.

Target GitHub Project: use the exact supplied URL or the uniquely established existing Project. Do not select a similarly named Project or create a competing one by assumption. If none exists, prepare the proposed configuration and ask only for the owner/creation decision needed to select its destination.

I authorize additive planning/documentation work and non-conflicting GitHub planning changes in the resolved target: create or reuse Plan/Task issues, repository labels, release milestones, native relationships, Project items/fields/views and narrowly scoped built-in Project automation where supported. Prepare the exact sync manifest first, then execute these authorized operations without another routine confirmation request. Respect platform review/tool approval controls.

Do not change application code, credentials, grants, environment settings, organization-wide schemas, branch protection or workflow definitions. Do not merge, deploy, dispatch workflows, invoke live sources/models, or assign implementation to Copilot or another coding agent. If documentation files need changes, use an isolated documentation workspace/branch and, where supported, open a normal documentation PR for review; do not merge it.

### 2. Read and reconcile before generating work

Read the current local versions below. Resolve these paths relative to this package directory; then reconcile them with the operative application records:

1. `ASKTD_SESSION_HANDOFF.md`.
2. `PRODUCT_DEFINITION_EN.md` and `QUARTERLY_PRODUCT_ROADMAP_EN.md`.
3. `ASKTD_PLAN_AND_LINEAGE_REFERENCE.md`.
4. `ASKTD_COPILOT_ARTIFACT_GENERATION_PROMPT.md` as the existing generation specification. This submitted prompt clarifies the current task and does not activate unrelated saved prompts.
5. `Roadmap-onepager.md` for the separate executive presentation namespace.
6. The maintained `MASTER_PLAN_V1(2).md` revision 2.1 proposed, `AskTD_Delivery_Plans_and_Dependencies.md` v0.2, and their available successors.
7. `AskTD_Product_to_Plan_Coverage_Review_2026-10-23.md`, or an accepted successor, as a review containing proposed corrections—not an adopted replacement Master.
8. `AskTD_Product_Guide_and_Delivery_Plan_EN_v0_3.md` for the English product and delivery explanation.
9. `ASKTD_LANGGRAPH_AND_LANGSMITH_PLAN.md` for the accepted technology selection, required telemetry and proposed task-level migration decomposition.

Also read ASKTD_SOURCE_CONNECTION_HEALTH_UI.md as the 26 October owner-requested UI capability. Preserve existing P02/P07 ownership, scoped P04/P05 inputs, R1 visibility and the 46-output register. Reconcile CONN-01–CONN-05 against current components/Tasks/PRs before allocating canonical work. Probe success, operational health, evidence maturity and required LangSmith collection remain separate. This reference does not expand this template’s activation/authorization scope or authorize live probes, credential changes or production actions.

Also inspect repository instructions, the operative application Master, ADRs, task/status indexes, newer Master candidates, relevant source/CI/deployment evidence, open and closed issues/PRs, Project fields/views, labels/milestones and earlier generation/sync reports. Do not assume a prior generation prompt was never run.

Record repository/root, branch/HEAD, worktree state and exact source revisions. Preserve staged, unstaged, untracked and other-worktree changes. Never reset, clean, stash or commit unrelated work. Do not assume the default branch includes unmerged work. Distinguish historical reports, directly verified evidence and unknown state. Classify each output as satisfied, partial, missing, unknown or superseded; unknown is not missing.

If a source or target is unavailable, complete independent portable planning work and identify the exact missing source/report or repository/Project information. Do not fabricate code absence, completion, IDs, dates, approvals or evidence URLs.

### 3. Preserve architecture and planning boundaries

- Preserve the full lineage: Master requirement/revision → engineering phase/slice → delivery Plan → named output → canonical Task/PR → acceptance evidence → release.
- P01–P15 are delivery Plans. Keep Master phases, detailed 2F slices, provisional 2G, executive Phases 1–3 and releases R1–R4 separate. Use the documented crosswalk and legacy aliases.
- Preserve accepted work and task IDs, including 2F.1 trace-only behavior. A proposed mapping is not proof of operative adoption or new execution policy.
- SQL and Databricks Registry bindings, compatible application authorization, execution contracts and readiness are baseline scope across P01/P02/P04/P05/P07. P15 covers further expansion.
- Retain App Service SQL system-assigned managed identity and application-enforced end-user authorization. Qualify actual Databricks identity/connector and each provider/environment separately.
- Preserve historical successful login and SQL identity validation. Reopen only where current regression evidence warrants it. Missing access or a 404 does not establish failure.

### 3.1 Include the owner-selected migration

The owner selected LangGraph primarily for future complex analytical graphs and made LangSmith telemetry mandatory. Carry the scoped amendment into P05/P06/P07 and relevant task acceptance; it supersedes earlier preserve-framework-only/exclusion wording only for this migration. Preserve the full proposed-Master adoption boundary.

Match the migration plan's MIG-01–MIG-08 candidates against existing team Tasks/PRs before allocating canonical IDs. They are local reconciliation keys, not existing issues or new outputs. Retain one accountable Plan per Task, exact existing named outputs, H/C/G dependencies, owner/reviewer roles and evidence. Separate the early P07 event/adapter contract from later integrated qualification. Do not make P05 and P07 whole-Plan mutual blockers or mark unqualified Tasks Ready.

Required acceptance includes a behavior-preserving path, bounded complex-graph proof, state/isolation/resume checks, payload-safe telemetry and actual LangSmith ingestion/read-back for environment qualification. An alternate sink or mocked exporter cannot mark mandatory LangSmith complete. This remains a planning task; do not implement, transmit telemetry, change credentials/settings, assign a coding agent or deploy.

### 4. Resolve the product-coverage findings

Prepare precise planning amendments and carry already documented behavior into task acceptance:

- **P10:** explicit application user/enabled-capability administration, separate from business-data rights. The proposed `P10.service_administration` is not an established output. Keep the current documented 46-output baseline unless an accepted successor or explicit decision adopts a new output. If ownership needs a decision, prepare the exact amendment and a bounded decision task; continue unaffected work.
- **P07:** demonstrate that authorized administrators can inspect operational, quality and usage information using an approved view/report. Event production alone is insufficient acceptance. Do not assume a custom dashboard is required.
- **P12:** pre-save schedule-frequency preview and evidence-dependent cost preview. Unknown estimates remain unavailable, not zero. Add only the selected P07/P10 producer inputs; do not block scheduling on all P10 work.
- **P07/P09/P13:** explicit permitted usage, outcome, clarification, feedback and template-version signals for the selected owner analytics. Preserve privacy and reviewed publication.
- **P05/P06/P08/P09/P12:** retain the rendered question/clarification/answer journey, presentation fidelity, no unsupported causal claims, historical answer versus explicit rerun, preference controls/precedence, no-code authoring and complete schedule editing/history acceptance.

Show each product clause's owning output, acceptance or conditional/decision-pending disposition. Distinguish approved requirements from review recommendations; do not silently resolve contested architecture or scope decisions.

### 5. Build a small, navigable issue model

Reuse or create one Plan parent issue for each P01–P15. Each Plan includes its outcome, outputs, boundaries, source lineage, release contributions, dependencies, acceptance and existing evidence links.

Create one canonical issue per actionable Task, under one accountable Plan. Additional contributing Plans/phases/outputs/releases are references, not duplicate tasks. Reconcile existing parentage; do not silently reparent human-managed work. Named outputs are stable references in task bodies and the canonical register; do not automatically create another issue for every output.

Cover all Plans at outcome/dependency level. Decompose only justified remaining work for the selected near-term end-to-end workflow. Keep later work at outcome/contract depth until selected. Where business input is pending, synthetic contract/framework work may proceed with explicit fixtures and limitations; business acceptance and live-provider qualification remain separate.

Every actionable Task must contain:

- Canonical ID allocated under the existing convention only after duplicate matching.
- One accountable Plan and exact named output references.
- Product clause; Master document/revision/requirement; established engineering anchor and mapping basis.
- Bounded objective, scope exclusions and existing-work disposition.
- Inputs and typed dependencies, including the exact consuming activity and satisfaction evidence.
- Implementation owner role, reviewer role and applicable decision owner; verified GitHub logins only where an approved roster/assignment exists.
- Provider/environment and actual source revision where applicable.
- Observable acceptance criteria, appropriate verification and expected evidence location.
- Release contribution, workflow state, evidence maturity and unresolved decisions.

Leave unknown assignments unassigned. Do not invent developers, capacity, estimates, dates or business values. Assigning a coding agent may start implementation and is outside this task.

### 6. Represent relationships correctly

Keep these relationships distinct:

| Relationship | Representation |
|---|---|
| Accountable Plan → Task | Native parent/sub-issue where supported; otherwise explicit links with the limitation recorded. |
| H: required output | Native `blocked by` only for an applicable unmet prerequisite of the specific consuming task/activity. Link to the actual producer Task, not an entire Plan by default. |
| C: shared contract | Typed coordination reference with agreed contract/version; not mutual blocking issues. |
| G: acceptance gate | Gate owner, scope and evidence; blocks applicable acceptance/activation, not unrelated preparation or synthetic tests. |
| O: conditional | Record condition and underlying H/C/G effect. Activate only when the selected scope makes it applicable. |
| Contributing requirements/outputs/phases/releases | Traceable links in the register/body and suitable fields; not automatic parentage or execution blockers. |

Validate the effective hard-dependency graph for accidental cycles. Separate early `P07.event_contract` from later `P07.acceptance_bundle`; avoid a whole-Plan P05↔P07 cycle. A task consuming `P08.saved_analysis` need not wait for all P08 preferences/history.

Retain typed dependencies and satisfaction evidence even where GitHub can display only a simple blocker. A Markdown link or label does not prove a native relationship was created. An issue being closed is not sufficient evidence that its output is accepted for every consuming scope.

### 7. Labels, fields, views and project visibility

Interpret “tags” as GitHub issue labels, not Git tags. Reuse existing compatible labels and issue types first. Keep a small taxonomy: a project label if needed; Plan/Task/Decision classification where issue types do not cover it; useful concerns such as security, data contract and observability. Optional `plan:P01`–`plan:P15` labels are for repository filtering, not a replacement for parentage. Avoid one label per task/output/person and duplicate status/priority labels when Project fields already own those values.

Reuse compatible Project fields. A suitable minimal model is:

| Field | Use |
|---|---|
| Status | Backlog, Ready, In progress, Review, Done, mapped to existing conventions. |
| Plan | P01–P15; distinct from engineering phase and release. |
| Primary output / engineering anchor | Optional text or existing field; full many-to-many mappings remain in the register/body. |
| Target release | Selected R1–R4 contribution; preserve additional contributions separately. |
| Priority | Existing vocabulary and justified value; otherwise unset. |
| Assignee | Verified human assignment. Reviewer/decision ownership remain separately recorded. |
| Acceptance/evidence | Evidence maturity for the stated scope; not inferred from issue closure. |
| Iteration / dates | Only real commitments supported by capacity and owner decisions. |

Track blocker reason, responsible role/person and next action through native dependencies and the existing board convention. Avoid conflicting copies of status. A single-select field cannot hold all engineering anchors or provider/environment evidence.

Create or configure supported views for: Plan/release coverage; ready developer work; blocked/decision-needed work; reviewer queue; acceptance gaps; and SQL/Databricks environment readiness. If a view requires unsupported fields or queries, provide exact manual setup steps rather than claim completion.

Define Ready using sufficient scope, required inputs, resolved applicable blockers and testable acceptance. Define Done by the task's own acceptance/evidence. Distinguish artifact state, work state and acceptance maturity. A synthetic framework task can be Done while business acceptance or live-provider readiness remains pending. A merged PR, closed issue or parent completion percentage does not establish release acceptance.

Inspect current Project automations before changes. Narrow built-in auto-add/status rules may be configured only for the resolved scope and explicit status semantics. Do not automatically mark newly added work Ready, equate every closure reason with successful completion, or infer product acceptance from PR merge. Preserve conflicting existing automation and report the conflict. Do not introduce workflow files, agent assignments or recurring autonomous triage as incidental setup.

Developer/project visibility and runtime observability are distinct: the Project tracks ownership, dependencies, review and evidence; P07 owns application operational observability. Connect their evidence links without claiming one proves the other.

### 8. Prepare and apply an idempotent sync manifest

Reuse existing planning files and generation reports within the detected application root and this `docs/roadmap/` package. Keep new generated planning records in an appropriate subdirectory of that package when needed; preserve existing canonical files and paths. Maintain one canonical lineage/dependency source with readable views. Avoid a competing tracker or unnecessary generator framework.

Before writes, produce reviewable issue bodies and a manifest listing each exact operation: Create, Update, Link existing, No change or Conflict. Include target, stable identity, expected current state, managed fields/sections, proposed changes and prerequisites. Match open and closed items by canonical IDs, known links and stable markers, not titles alone.

Use stable markers such as `<!-- asktd-plan:P04 -->`; reuse existing task markers. Preserve human-authored content, discussions, assignments, status, dates and unrelated metadata. Re-read immediately before updates and change only bounded managed sections/fields. Report concurrent conflicts; do not overwrite the whole issue body or assume atomic updates.

Apply authorized non-conflicting operations in dependency order: labels/compatible fields as needed; Plan identities; Task identities; relationships; Project membership/metadata/views. Record actual remote IDs/URLs and outcomes immediately. On a timeout or uncertain result, inspect by stable identity before retrying. Reruns must reuse previous successes.

Check actual Issue, label, relationship and Project capabilities separately. Prefer supported GitHub tools; use authenticated CLI/API when available and appropriate. Verify installed command/API support before executing. Do not expose tokens or attempt to bypass access controls. If an operation is unavailable, finish supported work and retain its exact pending payload/manual steps. GitHub's issue-draft UI may require the owner to submit drafts; report drafts as drafts until submission is verified.

### 9. Deliver and verify

Produce/reconcile the existing artifact package: planning index, baseline report, all Plan documents, canonical lineage/output dependency register, product coverage and release/acceptance matrices, provider readiness matrix, first executable Task set, issue bodies, sync manifest and generation report.

Check that all 15 Plans are represented; output references and aliases resolve or are explicitly unresolved; no task is duplicated; parentage and dependency directions are correct; conditional edges survive; coverage refinements are resolved or scoped decisions; and the SQL/Databricks baseline remains visible. Use proportionate document/data checks. Do not run the application or dispatch workflows for this planning task.

Read back actual remote results for mutations performed. Report separately: created, updated, reused, draft-only, pending, failed and conflicted. Provide actual issue/Project/PR URLs, counts by operation, source revisions, unresolved decisions and the next smallest ready task with prerequisites and acceptance.

Include a reusable maintenance instruction: on an explicit refresh request, reconcile new issue/PR/evidence state, update supported managed fields, surface newly ready work and blockers, and report acceptance gaps. Do not pretend this prompt creates continuous background project management. Recurring automation is a separate explicitly selected setup.

## End prompt

## Follow-up prompt for an explicit project refresh

```text
Refresh the existing AskTD Project using its established canonical register and last sync report. Reconcile changed issues, PRs, dependencies and acceptance evidence. Update only authorized managed fields and links; preserve human decisions and avoid duplicate work. Report ready tasks by verified owner, blocked tasks with blocker owner/next action, review queue, stale or missing evidence and release-gate gaps. Do not start coding, expand scope, invent dates or treat a merged PR/closed issue as business acceptance. Return actual changes and unresolved conflicts.
```

## Local references and capability qualification

- [Generation specification](ASKTD_COPILOT_ARTIFACT_GENERATION_PROMPT.md).
- [Plan and lineage reference](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md).
- [Product definition](PRODUCT_DEFINITION_EN.md).
- [Quarterly product roadmap](QUARTERLY_PRODUCT_ROADMAP_EN.md).
- [Maintained proposed Master](<MASTER_PLAN_V1(2).md>).
- [Delivery portfolio](AskTD_Delivery_Plans_and_Dependencies.md).
- [Product coverage review](AskTD_Product_to_Plan_Coverage_Review_2026-10-23.md).
- [English product and delivery guide](AskTD_Product_Guide_and_Delivery_Plan_EN_v0_3.md).

The local package defines the planning requirements. Native issue relationships, Project fields/views, automation and write operations remain subject to the executing GitHub environment and granted capabilities. Inspect those capabilities at execution time and report unsupported operations accurately. No external documentation link is required by this prompt.
