# AskTD framework development continuation
Prepared: 22 October 2026 (America/Toronto)
Amended: 26 October 2026 for the owner-selected LangGraph migration and mandatory LangSmith telemetry.
Status: Prepared implementation brief; no application implementation or test result is claimed by this file.
Audience: The coding agent in the existing connected AskTD application session.
Activation: This implementation task applies only when explicitly submitted. Reading it from the planning package does not authorize code changes. Planning synchronization uses [AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md](AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md).

## Objective and scope

Continue the existing AskTD / AskAlpha application. The owner wants software development to proceed while Deposits business input is pending. Complete the demonstrated remaining, business-independent R1 framework work using clearly synthetic fixtures, so approved business definitions and provider bindings can later be onboarded through explicit contracts.

Deliver runnable behavior in the existing application, meaningful verification, and an accurate remaining-dependencies report. Do not replace the application with a new scaffold or stop at interface stubs while claiming completion. Preserve completed work. This is a bounded R1 framework task, not authorization to build all R2–R4 capabilities.

Business input is pending, not waived. Engineering readiness, live-provider qualification, business acceptance, pilot acceptance, and production release are separate states. New business requirements may still require further code; do not promise configuration-only onboarding for every unknown requirement.

Work in English. Use one implementation writer for shared files; independent read-only reviews may run in parallel.

## 1. Reconcile before editing

Use the actual connected application repository. Read its applicable instructions, operative Master, ADRs, task/status indexes, current task, relevant code/tests, open and closed PRs, and any planning-generation report. Inspect before assuming the Copilot artifact-generation prompt has or has not run.

Record:
- Repository URL, actual application root, active branch and HEAD.
- Worktrees and staged, unstaged and untracked changes; preserve newer Master candidates.
- Applicable existing Task/PR IDs and their status, without reopening completed work automatically.
- Existing provider, Registry, authorization, execution, rendering, context and observability behavior.
- Relevant test evidence with code revision and date; distinguish historical reports from results run now.

Do not reset, clean, stash, discard or commit unrelated changes. Inspect other refs read-only. Where edits would overlap active work, use an appropriate isolated worktree or coordinate ownership while preserving the actual current baseline. Do not silently switch to main or a historical checkpoint.

Read the current repository-local documentation package beside this file. Its intended installed location is `docs/roadmap/` beneath the detected application root. Resolve the actual root from repository instructions and source structure, record the active branch/HEAD, and distinguish a staged package from the application source. Read:
1. ASKTD_SESSION_HANDOFF.md
2. PRODUCT_DEFINITION_EN.md
3. QUARTERLY_PRODUCT_ROADMAP_EN.md
4. ASKTD_PLAN_AND_LINEAGE_REFERENCE.md
5. ASKTD_COPILOT_ARTIFACT_GENERATION_PROMPT.md and AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md as background only
6. Roadmap-onepager.md for the executive namespace
7. MASTER_PLAN_V1(2).md and AskTD_Delivery_Plans_and_Dependencies.md
8. AskTD_Product_Guide_and_Delivery_Plan_EN_v0_3.md
9. AskTD_Product_to_Plan_Coverage_Review_2026-10-23.md.
10. ASKTD_LANGGRAPH_AND_LANGSMITH_PLAN.md, including current team-work reconciliation, staged migration and task-level dependencies.

The maintained MASTER_PLAN_V1(2).md revision 2.1 is proposed until reconciled with the operative Master and any newer candidate. The portfolio v0.2 and English guide v0.3 are supporting references. Coverage recommendations remain proposed; they do not authorize new outputs, business policy or implementation scope without the applicable decision. The package does not establish the current application revision or deployment.

Historical application access was unavailable during the documentation review; this proves neither missing code nor failure. If the actual application cannot be accessed now, return the exact access/baseline limitation and available report. Do not create a substitute application.

Reading saved prompts does not execute them. This continuation brief supplies an implementation task only when explicitly submitted.

## 2. Preserve accepted behavior

- Apply the owner-selected LangGraph migration within ASKTD_LANGGRAPH_AND_LANGSMITH_PLAN.md. Preserve the hosting boundary, supported APIs, working behavior, controls and reusable application services. Reconcile the team's current migration before implementing only remaining work. Diagram labels do not authorize unrelated infrastructure or framework changes.
- LangSmith telemetry collection is mandatory for the migrated scope. Establish the permitted event/export contract early; mock/synthetic evidence supports development but does not replace actual qualified ingestion. Keep audit and metering obligations distinct. This implementation template still does not authorize live telemetry transmission or environment changes.
- Preserve successful historical login and SQL identity validation. Reopen only when current evidence shows a relevant gap or regression.
- Preserve App Service SQL system-assigned managed identity and application-enforced end-user authorization. Native workload grants remain required. Qualify Databricks identity and connector separately.
- SQL and Databricks Registry bindings, compatible authorization, execution contracts and readiness are baseline P01/P02/P04/P05/P07 scope. P15 is further expansion.
- Preserve 2F.1 classification-only, trace-only behavior, default-OFF semantics and accepted repairs; do not activate it as part of this task. Preserve any later accepted activation evidence without resetting it. Do not introduce expiry, approval authority, renewal or REVIEW_REQUIRED enforcement without the applicable decision. 2F.1a is conditional on present need; 2G remains provisional.
- Reuse existing AST/object-scope/read-only guards. A passing synthetic test does not justify widening real permissions.
- No silent fallback to broader credentials, another provider, unrestricted SQL or a fake successful answer.
- No cross-provider joins, automatic metadata certification, production self-rewrite, compulsory Graph DB/Redis, or new live enterprise integrations.
- Keep optional caches, persistent history/preferences, owner authoring, schedules and exports outside this first framework scope unless already active and needing directly affected compatibility protection.

## 3. Establish the gap register and ownership

For each applicable output, classify: satisfied, partial, missing, unknown or superseded. Link evidence and an existing canonical Task/PR where available. Unknown is not missing.

Use this lineage:
Master requirement/revision -> engineering phase/slice -> delivery Plan -> named output -> canonical Task/PR -> acceptance evidence -> release.

P01–P15 are delivery Plans; engineering phases, 2F slices, executive phases and releases are separate namespaces. Retain legacy aliases and actual task IDs.

| Work area | Accountable Plan/output | Work possible with synthetic inputs | Evidence still needed later |
|---|---|---|---|
| Input/reference case structure | P01.scope, P01.reference_cases, P01.provider_coverage, P01.acceptance_owners | A validated intake format and clearly illustrative cases | Approved question set, calculations, coverage and accountable reviewers |
| Current access contracts | P02.scope_contract, P02.enforcement_evidence | Existing enforcement integration and allowed/denied/unresolved/revoked scope tests | Approved entitlement mapping and real environment evidence |
| Provider connection boundary | P02.sql_route, P02.databricks_route | Configuration validation and connection/error contracts using test doubles | Actual route, identity, grants, network and environment qualification |
| Semantic intake and bindings | P04.semantic_bundle, P04.bindings, P04.relationship_evidence, P04.publication_contract | Schema, loading, validation, version/compatibility behavior and synthetic provider mappings | Business certification, actual mappings and any required join evidence |
| End-to-end analytical execution | P05.analysis_contract, P05.result_contract, P05.adapter_behavior | Bounded planning/recipe execution, adapter contracts and normalized results | Real dialect/driver/endpoint evidence and business correctness |
| Answer presentation | P05.curated_templates, P05.correctness_evidence | Deterministic output from validated synthetic results | Approved reference answers and scoped live/model acceptance where applicable |
| Clarification and follow-up | P06.context_contract, P06.followup_behavior, P06.context_evidence | Compatible same-session state and access rechecks | Agreed business follow-up scope |
| Operations/evidence | P07.event_contract, P07.metering, P07.support_contract, P07.feedback, P07.provider_readiness, P07.acceptance_bundle | Safe correlation, bounded feedback, attempt accounting, failure behavior and evidence recording | Accepted telemetry route, service targets, support ownership and actual provider observations |

These are contributing outputs, not whole-Plan completion claims. Keep P03.policy_decision and P03.lifecycle_disposition unresolved where owner decisions are unavailable; do not fabricate P03.selected_enforcement.

## 4. Implement the smallest runnable path, then remaining applicable gaps

The first integrated slice is owned by P05, contributing to P05.analysis_contract, P05.adapter_behavior, P05.result_contract, P05.curated_templates and P05.correctness_evidence. Link contributing P02/P04/P06/P07 outputs to their existing canonical tasks; do not assign several accountable Plans to one task or mark the whole of P05 complete from this slice.

Use the migration plan's staged sequence and existing canonical Tasks. A node may be deterministic; retain selective approved model assistance. Define graph/state versions, node input/output contracts, conditional edges, explicit validation and safe termination. Include bounded synthetic complex-graph and interruption/resume evidence before claiming the migration supports future complexity.

Start with a representative synthetic comparison of two reporting periods. Use fictional data and neutral names; label the dataset and displayed results as synthetic. Keep an independently calculated expected answer.

Reuse existing intake and storage patterns. Do not invent a new configuration format when an adequate contract already exists. At minimum, support the required fields for logical metric/dataset/field IDs, units, grain, periods/time semantics, dimensions, recipe references, versions, provenance, provider bindings and output context. Represent unavailable business decisions as pending, not as fake approvals or permissive defaults.

Demonstrate:
- Load and validate a synthetic semantic/recipe bundle.
- Resolve the permitted question and current scope.
- Clarify a missing period or ambiguous request rather than guessing.
- Produce a validated analytical request and bounded provider execution.
- Normalize and validate returned data.
- Render a deterministic answer/table with metric, units, periods, filters, source, data-as-of and versions.
- Handle one compatible follow-up with current access rechecked.
- Emit safe correlation and usage/failure evidence through the required LangSmith adapter using a test double unless real transmission is separately authorized and qualified.
- Prove conditional routing, independent branch/join behavior, bounded recovery and access-checked resume using synthetic fixtures as specified by the migration plan; this does not activate new business scope.

Exercise the real application boundaries with test doubles where needed. Preserve production authentication; test principals belong only in the existing test harness or an explicit local-only demonstration configuration. Do not introduce an unauthenticated production demo route.

Any simulated approval evidence belongs only in isolated synthetic fixtures and must be visibly identified as test evidence. It cannot be published into a live Registry or satisfy a production approval gate. Preserve the real approved-recipe gate and keep missing approval decisions explicit.

Where the real provider route is sufficiently specified, implement demonstrated missing adapter behavior through the existing interfaces. Where identity, connector or execution semantics are unresolved, finish the common contract and tests and mark that provider integration pending. Mocked responses are not SQL/Databricks execution qualification.

After the first complete path works, finish the remaining demonstrated gaps required for this bounded R1 framework. Do not fill the waiting period with unrelated features.

## 5. Required acceptance evidence

Use focused tests appropriate to the actual code change and existing required gates. Include these cases where affected:
- Correct result versus an independent synthetic reference calculation.
- Allowed, denied, unresolved and revoked scope; user/session isolation.
- Read-only validation, allowed objects, parameter handling, row/time bounds, cancellation and safe provider failures.
- Provider-specific parameter/dialect/type/decimal/null/date behavior at the level actually exercised; label mocks separately from real adapters and live endpoints.
- Invalid or ambiguous bindings rejected; dependency-specific incompatibility handled safely; unrelated Registry/version changes do not automatically invalidate recipes. Unknown business inputs cannot masquerade as approved content.
- No-data, unavailable source, invalid result and zero-baseline comparison handled without invented values or success.
- Values, signs, units, scope, periods, warnings and source/as-of remain intact through presentation.
- Follow-up changes only intended compatible context; topic changes and current access are handled safely.
- Safe error/correlation records, no unapproved raw data in model payloads/logs, bounded model/retry behavior, and missing usage reported as unknown rather than zero.
- If a demonstrated gap justifies 2F.1a safe-error hardening, verify both actual model-helper outbound boundaries, including retry/error paths, with synthetic sentinels and mocked calls. Do not implement it automatically from an old next-task note.
- Existing lifecycle and working login/SQL behavior preserved.
- Substitute a second valid synthetic semantic/binding bundle through the supported intake path without changing unrelated orchestration. Document any necessary extension rather than hiding it.

Use synthetic data and mocked model boundaries. Do not dispatch remote workflows, change cloud permissions, query real banking data, merge or deploy as part of this task. Do not add a requirement to run the entire suite solely for documentation; broaden verification for a concrete risk or mandatory repository gate.

## 6. Definition of framework readiness

Claim readiness only for the explicit tested scope when:
1. The existing application runs the complete synthetic workflow.
2. Definitions and bindings enter through validated, versioned contracts.
3. The selected security, result and failure cases have reproducible evidence.
4. Known provider/domain gaps are explicit and cannot silently activate as successful production behavior.
5. The team has concise local run/test instructions and a business intake checklist.
6. A second synthetic content bundle demonstrates the intended separation between engine and content.

Record each provider separately as contract designed, code implemented, synthetic/adapter verified, or environment qualified. Also record business acceptance separately. Never promote all these states from a single passing test.

## 7. Deliver and report

Update the existing relevant engineering documents and task/evidence records within the actual application workflow. Do not create duplicate plan issues or synchronize a guessed GitHub Project. Local implementation and verification can proceed without a Project ID.

Report:
- Actual repository, root, branch and HEAD; preservation of existing changes.
- Baseline sources and relevant current Task/PR links.
- What was already complete and reused.
- Files and behaviors actually changed.
- Commands executed and exact test outcomes, with evidence revision.
- A short demonstration of the synthetic end-to-end result.
- Plan/output/engineering lineage for each delivered slice.
- Separate SQL and Databricks evidence levels.
- Remaining business, policy, environment and approval inputs.
- The next smallest justified activity.

If application access is unavailable, return a compact current-session report instead: repository URL, root, branch/HEAD, worktree summary, operative Master revision/path, newer Master candidate if any, current task and relevant PR states, existing implementation/test evidence, and exact inaccessible sources. Do not include credentials, tokens or banking data.

For migrated scope also report graph/state version, existing team Task/PR reuse, parity/complex-graph evidence, LangSmith adapter versus real-ingestion status, pending environment decisions and rollback readiness. Do not claim the framework, migration, LangSmith qualification, pilot or production is complete unless its corresponding evidence exists.

