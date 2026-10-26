# AskTD — LangGraph migration and required LangSmith telemetry

**Document ID:** ASKTD-LANGGRAPH-LANGSMITH-PLAN\
**Version:** 1.0\
**Decision date:** 26 October 2026, America/Toronto\
**Status:** Owner-directed technology selection; delivery design to reconcile with current application work. Implementation and environment qualification are not established by this document.\
**Accountable delivery areas:** P05 orchestration; P06 session continuity; P07 telemetry and evidence.

## 1. Decision and authority

The owner has selected **LangGraph for AskTD orchestration**. The primary reason is to support more complex, stateful analytical graphs in future. Better observability is a supporting benefit, not the sole rationale. **LangSmith telemetry collection is a required part of the migration**, not an optional later integration.

This decision supersedes earlier preserve-framework-only wording and the broad framework-migration exclusion **only for the bounded migration described here**. Preserve working application behavior, contracts, accepted controls and later team work. The owner reports that the team has already been asked to migrate; inspect its current ADRs, branch, Tasks and PRs before creating replacement work. Do not restart a migration that is already underway.

This amendment does not promote the complete proposed Master revision 2.1, retire valid historical revisions, or establish application implementation, enterprise service approval, deployment or release. Reconcile the operative Master and any newer candidate. Record this decision in the application's existing ADR convention without inventing an ADR number or rewriting historical decisions.

The baseline [Master](<MASTER_PLAN_V1(2).md>) §§4.2–4.3 and 8, [lineage reference](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md) §§6.5–6.7 and [portfolio](AskTD_Delivery_Plans_and_Dependencies.md) remain applicable with this narrow amendment. P01–P15, the 46 named outputs, existing 25 portfolio dependency records, legacy aliases and release namespaces are preserved. The task-level dependencies below supplement those records; they do not redefine their counts.

This is an English planning document, not an execution prompt. Publishing it does not create issues, configure a Project, start a coding agent, alter permissions, invoke sources/models, merge or deploy.

## 2. Target architecture and boundaries

Use an explicit LangGraph Graph API orchestration layer with typed state and named, versioned node contracts. Reconcile the precise API and dependency versions with the existing Python runtime and team implementation. Keep domain calculations, Registry access, validators, provider adapters and formatting behind reusable application interfaces; graph nodes call those interfaces.

The coordinator owns transitions, cancellation, budgets and completion. It does not need an LLM for every transition. A model may propose a structured interpretation or analytical plan; deterministic checks remain responsible for supported operations, current scope, approved semantics and execution bounds. A node is not automatically an autonomous agent or a model call.

| Component | Responsibility | Preserved boundary |
|---|---|---|
| Request and authorization boundary | Authenticate, resolve effective scope and establish a run | Application-enforced authorization; no authority inferred from graph state |
| Intent and clarification subgraph | Resolve meaning or request missing information | No guessed business definition; recheck access on resume |
| Semantic and planning subgraph | Resolve Registry references; select an approved recipe or bounded candidate plan | Templates reference definitions; models cannot publish or approve semantics |
| Validation and execution subgraph | Validate the candidate; execute approved bounded operations through existing adapters | Read-only/object/parameter guards; SQL and Databricks qualified separately |
| Result and presentation subgraph | Validate values and context; choose eligible output formatting | Numeric, unit, grain, scope, version and as-of fidelity |
| Telemetry adapter | Send eligible execution events to LangSmith and expose collection failures | Allowlisted payloads; separate audit, usage and product records |

Map the actual existing route to the Master §4.3 sequence: authorization and permitted context; intent/template/clarification; eligible early reuse; Registry/recipe or bounded planning; validation; eligible post-plan reuse; bounded execution; result validation; presentation and final checks. Preserve current route-specific skips. An early lookup must not depend on a plan hash that has not been produced. Existing optional reuse features do not become mandatory cache infrastructure through this migration.

Retain the approved hosting/API boundary, source-neutral contracts, App Service SQL system-assigned managed identity and end-user scope enforcement. Qualify the actual Databricks identity and connector independently. LangGraph selection does not require LangSmith-hosted application deployment, a new service topology, Redis, PostgreSQL, a graph database, new model purposes, cross-provider joins or automatic business actions. Select any necessary persistence infrastructure through the normal environment decision with an explicit owner.

## 3. Graph and state contract

Define one versioned graph contract for the selected route, with subgraphs where they clarify ownership and reuse. For every node record its stable identity, input/output schema, permitted state updates, caller/return relationship, execution eligibility, failure categories, timeout, cancellation, retry budget and telemetry mapping. Link existing model-call IDs instead of inventing a new inventory disconnected from source evidence.

The internal state contract must identify:

- Run, turn and isolated session/thread references; graph and state-schema versions.
- Current authorization reference and evaluation version; credentials and tokens are never serialized into checkpoints.
- Intent, unresolved clarification and bounded permitted context.
- Metric, recipe, template, Registry and binding references with relevant versions; parameters, period, units and grain.
- Candidate-plan identity, validation outcome and executable operation references.
- Dependency completion, branch outputs, result references, source freshness and final outcome.
- Actual attempt counts, time/query/model budgets, cancellation and safe error categories.

State fields are not all eligible telemetry fields. Models receive only the minimum approved inputs for their purpose. Trace/Registry references are not access grants. Protected state must be authorized before loading; recheck current access and relevant versions before resumed execution or protected output. A stored approval is evidence of a past decision, not perpetual execution authority.

Specify conflict handling for concurrent sessions and parallel branches. Prefer separate branch outputs and an explicit validated join; where reducers merge state, define their rules and test them. Define checkpoint retention, access, deletion, schema migration and behavior for in-flight runs when graph versions change. Checkpoints are execution state, not automatic P08 saved history or personal memory.

## 4. Stage the migration around evidence

1. **Reconcile and establish parity cases.** Inspect team work and capture current source-backed behavior, controls, model/query attempts and reference results. Reuse an existing migration Task/ADR when present.
2. **Agree graph and telemetry contracts together.** Define state/node/edge contracts, collection payloads, failure handling and measurement criteria before instrumenting all nodes. Synthetic preparation need not wait for Deposits sign-off or live telemetry access.
3. **Migrate one representative path.** Wrap existing application services in the graph; compare outputs, authorization and errors against independent expected results and valid baseline evidence. Instrument this first path through the LangSmith adapter.
4. **Prove the graph can grow.** Add a bounded synthetic graph with branching, dependency-aware joining, clarification/resume and a bounded retry or repair path. This is required architectural evidence, not permission to launch an unapproved business capability.
5. **Qualify and expand.** Collect real LangSmith ingestion/read-back evidence in the selected permitted environment, complete provider-specific regressions, measure overhead, rehearse rollback and migrate remaining justified routes. Resolve enterprise decisions before enabling the affected route.

An illustrative complex case is: compare monthly balances, independently calculate approved product contributions to the change, then join the validated outputs into one explanation. Use a single approved provider context for each example. Product contribution is arithmetic attribution, not proof of business causation. All example definitions and data remain synthetic until approved.

The complex-graph proof must demonstrate actual conditional branches, selective model assistance, independent work that may run concurrently, joins that wait for all required inputs, and safe behavior when a required branch fails. Optional branch failures must be explicitly represented; they cannot silently produce a complete answer. Add bounded loops only for classified recoverable conditions, with a stop condition and shared attempt/time budget. Do not retry permission denials, unsupported semantics or invalid approvals as transient failures.

For resume, prove user/session isolation, current access checks, version compatibility and handling of already-completed work. Checkpointing alone does not establish exactly-once behavior: repeated provider/model attempts and later side effects require explicit replay/idempotency rules. Test restart recovery with the selected persistent mechanism before claiming durable recovery; an in-memory demonstration is insufficient. Do not run both old and new paths against live models/providers merely to compare them without separate workload authorization.

## 5. Required LangSmith telemetry contract

LangSmith is the required application/agent execution telemetry destination for the migrated scope. Local logs, an SDK import, a configured key or a mocked exporter do not satisfy environment qualification. Infrastructure monitoring, required security/data audit and authoritative usage accounting remain distinct obligations; correlate them without treating the LangSmith trace as a replacement for all records.

| Signal group | Required eligible evidence |
|---|---|
| Trace structure | Root request/run, child node/model/tool attempts, parent-child relationships, subgraph identity, branch decisions and resume correlation |
| Control flow | Executed/skipped/reused stages with safe reason codes; validation outcomes; clarification; cancellation; safe terminal status |
| Versions and context | Application revision, graph/schema version, environment, provider route and permitted semantic/template references |
| Performance and economics | End-to-end and node latency, actual model/query/retry attempts, available token usage and labelled cost estimates; unavailable values remain unknown |
| Collection health | Export failures, bounded queue/backpressure behavior, dropped or unsampled counts, retry/flush outcome and visible collection gaps |

Approve an allowlist before export. Keep raw questions, prompts, conversation messages, SQL, query results, customer identifiers, credentials, full state and exception bodies out of default telemetry. Use opaque correlation identifiers and safe reference IDs only where approved; a hash or pseudonym is not automatically non-sensitive. Check metadata, tags, run names, auto-instrumented nested calls, retry/error paths and exporter diagnostics as well as top-level inputs/outputs. Masking must occur before transmission, and synthetic sentinel tests must inspect the outbound boundary. Do not collect hidden model reasoning.

The selected environment needs a recorded LangSmith organization/project or equivalent deployment boundary, endpoint/hosting choice, authentication/secret handling, access roles, retention/deletion, permitted data residency/egress, owner, capacity/licensing and support arrangement. Reuse an approved integration if present. This plan does not select SaaS versus self-hosting or assert enterprise approval. If unavailable, continue synthetic implementation and keep LangSmith qualification pending; an alternative sink must not silently mark the mandatory requirement complete.

Define instrumentation coverage for every migrated route. Any sampling policy must identify covered events, exclusions and reconciliation of counts; unsampled events are not successful ingestion evidence. For acceptance cases, verify the required sanitized trace in LangSmith and reconcile its attempts/transitions against independent test expectations.

**Recommended outage behavior:** bounded asynchronous collection with visible failures and a defined retry/flush policy; maintain the required audit and controls independently. Do not hang requests indefinitely, accumulate an unbounded buffer, leak payloads into fallback logs or convert missing telemetry to successful collection. Whether a request may continue during a telemetry outage is an explicit operations/security decision for the affected scope. Any required-audit failure retains its existing fail-closed behavior. A degraded local path is not full LangSmith acceptance.

Use a synthetic/reference evaluation dataset to compare migrated behavior, routing, validation and cost/latency with the baseline. LangSmith experiments are useful supporting evidence. Deterministic calculations and approved business reference answers remain the correctness authority; an LLM judge is neither mandatory nor a substitute. Automatic prompt/code remediation and model-based online evaluation require their own selected scope and payload approval.

## 6. Output ownership and dependency-aware task candidates

Retain the existing lineage: Master requirement/revision → engineering phase/slice → delivery Plan → named output → canonical Task/PR → acceptance evidence → release. The primary architecture anchor is D15 with Master §§4.2–4.3 and 8; context and telemetry also use their existing D05/D06/D10/D11/D12/D14/D17/D18 mappings as applicable. Resolve actual engineering Task anchors from current source records; this amendment creates no new numbered engineering phase.

The following local keys are reconciliation candidates, **not issue IDs, new named outputs or reported assignments**. Match existing Tasks first, then allocate canonical identities under the application's convention. Each Task has one accountable Plan; keep cross-Plan contributions as references. Implementation owner/reviewer roles must be mapped to a verified roster before assigning individuals. No dates or capacity are assumed.

| Local key / candidate | Accountable Plan and existing outputs | Required input / dependency | Acceptance artifact and responsible roles |
|---|---|---|---|
| MIG-01 — Reconcile migration and ADR | P05: `P05.analysis_contract` | Current application Master/ADRs, team branch/PRs, control and call inventory; owner direction in §1 | Existing-work disposition and scoped ADR; backend lead with architecture review |
| MIG-02 — Define graph/state contracts | P05: `P05.analysis_contract`, `P05.result_contract`, `P05.adapter_behavior` | H: MIG-01 resolved affected baseline; C: P02 scope, P04 bindings, P06 context and MIG-03 event schema | Versioned node/state/transition contracts and parity fixtures; backend with QA and contract-owner review |
| MIG-03 — Define and implement telemetry adapter | P07: `P07.event_contract`, `P07.metering`, `P07.support_contract` | H: reconciled call/event inventory; C: MIG-02/MIG-05 identifiers; G: approved export envelope before real transmission | Allowlisted schema, synthetic outbound/redaction/failure tests, qualification checklist; observability engineer with security/operations review |
| MIG-04 — Migrate first analytical path | P05: `P05.analysis_contract`, `P05.result_contract`, `P05.adapter_behavior`, `P05.curated_templates`, `P05.correctness_evidence` | H: MIG-02 contract, MIG-03 adapter contract/test double, selected P02/P04 interfaces; P01 synthetic/reference cases | Runnable graph path, parity and negative-case evidence; backend with independent QA review |
| MIG-05 — Clarification and safe resume | P06: `P06.context_contract`, `P06.followup_behavior`, `P06.context_evidence` | H: MIG-02 contracts and MIG-04 integration seam; G: selected persistence/access/retention decision for durable environment claim | Interruption, revoked-access, isolation, restart and in-flight-version evidence; backend with QA/security review |
| MIG-06 — Prove bounded complex graphs | P05: `P05.analysis_contract`, `P05.correctness_evidence` | H: MIG-04 path and MIG-05 resume behavior; C: MIG-03 trace mapping | Synthetic branch/join, failure, bounded-loop, cancellation and attempt-accounting evidence; backend with architecture/QA review |
| MIG-07 — Qualify LangSmith collection | P07: `P07.event_contract`, `P07.metering`, `P07.provider_readiness`, `P07.acceptance_bundle` | H: MIG-03 adapter and selected MIG-04/05/06 route evidence; G: environment/export approvals, access and service configuration | Actual sanitized ingestion/read-back, collection-health and outage evidence; observability/operations with security/QA review |
| MIG-08 — Cutover readiness and rollback | P05: `P05.adapter_behavior`, `P05.correctness_evidence` | H: affected MIG-04/05/06 evidence; G: MIG-07 qualification plus relevant P02/P04/P01 and release acceptance | Route-by-route readiness, measured benefit/overhead, rollback rehearsal and retained old-run policy; backend with QA/operations review |

H means an actual required producer output for the stated activity; C is shared-contract coordination; G blocks affected acceptance/activation. Contract drafting and test doubles can proceed before environment qualification. MIG-03 and MIG-07 deliberately separate early telemetry implementation from later integrated evidence, avoiding a whole-Plan P05↔P07 cycle. A P07 qualification claim records LangSmith separately from SQL and Databricks; it does not qualify a data provider.

Do not mark all eight candidates Ready by copying this table. Record matched Tasks, exact evidence, pending decisions and only genuinely unmet hard prerequisites. R1 receives compatible framework work where selected; new complex business capabilities keep their own approved release scope. This amendment adds no fixed release date.

## 7. Acceptance and completion boundary

For the migrated scope require:

- Correct approved/synthetic reference results and preserved units, periods, grain, versions, source/as-of and effective scope.
- Correct recipe, bounded-planning, clarification, unsupported and denied routes; no model/tool/source calls on paths that must stop or skip them.
- Existing SQL safety, provider contracts, authorization and lifecycle behavior preserved, with separate SQL/Databricks evidence and no cross-provider join implied.
- Safe resume after access or relevant version changes; session isolation; deterministic join behavior; bounded loops/retries/timeouts; cancellation and replay handling.
- A real required LangSmith trace read back for the selected qualified environment, correct parent/child ordering and attempt counts, and outbound payload/privacy evidence including error paths.
- Measurements for latency, model/query attempts, cost availability and trace completeness/overhead against the recorded baseline; agree workload and thresholds before acceptance, without inventing improvements.
- A source revision, graph/state version, fixture/test evidence, integration disposition, support owner and rollback evidence for each claim.

Track planning, implementation, synthetic verification, environment qualification, business acceptance and release separately. Passing documentation checks or mock tests cannot close LangSmith ingestion, live provider qualification or business sign-off. Cutover/deployment remains an explicit release action under the existing process, outside this documentation submission.

## 8. Evidence basis and next action

**Directly established:** the owner's 26 October selection of LangGraph, complex-graph extensibility as the primary purpose, and mandatory LangSmith telemetry. The package baseline before this amendment was `aad03c8fd232a77612c8dd47d776083cebf70e2c`; this is a documentation revision, not an application HEAD.

**Supporting technical references reviewed on 26 October 2026:** official LangChain documentation titled *LangGraph overview*, *Workflows and agents*, *Persistence*, *Functional API overview*, *LangSmith Observability*, *Prevent logging of sensitive data in traces*, and *LangSmith Evaluation*. These support framework capabilities, not AskTD completion or enterprise approval. References are named without external links to retain package portability. Pin and verify the actual SDK/checkpointer/adapter versions during MIG-01/MIG-02.

**Still unverified here:** current application implementation/ADRs/PRs, actual graph migration status, selected persistence backend, LangSmith account/endpoint and approvals, live ingestion and rollout. Missing evidence is not evidence of missing code.

**Next smallest activity:** reconcile the team's current migration and record the bounded ADR under `P05.analysis_contract` (MIG-01). Reuse completed work, identify only remaining Tasks, then baseline graph and telemetry contracts in coordination. Do not rerun the historical Master-lineage investigation or reopen successful login/SQL work without new evidence.
