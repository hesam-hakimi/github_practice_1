# AskTD / AskAlpha — Master Product and Delivery Plan

**Document ID:** `MASTER_PLAN_V1`  
**Revision:** 2.1 — proposed consolidated update with continuity amendment  
**Updated:** 26 October 2026; scoped owner-directed technology amendment\
**Package edition:** 26 October 2026. Revision 2.1 remains proposed; the separate owner-directed LangGraph/LangSmith amendment below changes only its stated technology scope.\
**Previous revision:** 2.0 proposed, 19 October 2026  
**Status:** Proposed program reference; business commitments and release approvals remain subject to the relevant owners.  
**Audience:** Product, Deposits business owners, architecture, engineering, security, IAM, data governance, QA, platform, operations, Finance, and implementation agents.  
**Purpose:** Connect the product promise, architectural decisions, engineering work, quarterly outcomes, ownership, and release evidence in one plan.

> **This is a documentation update, not a project restart or a release authorization.** Preserve accepted work and later progress. Phase 2F.1 is a historical reported planning checkpoint; this update does not establish today's application HEAD, PR #18 merge status, deployed features, or production readiness.

This draft updates the revision 1.6 shown in the supplied screenshots. It incorporates the September architecture reconciliation and October product documents. It retains the original fourteen-section structure and engineering-phase history, while adding the agreed user-facing capabilities and a separate executive delivery view. The proposed document revision does not renumber engineering phases.

### Reading guide

**Product and business:** Sections 2–3 and the release table in Section 9.  
**Architecture and engineering:** Sections 4–8, the detailed 2F sequence in Section 9, and Appendix B.  
**Delivery and approvals:** Sections 9–14.  
**Changes and evidence:** Appendices A and C.  
**Adoption in the development branch:** Appendix D.  
**Delivery Plan lineage and session continuity:** Section 9.6 and Appendix E.

## 26 October 2026 owner-directed technology amendment

The owner selected LangGraph for orchestration, primarily to support future complex analytical graphs, and made LangSmith telemetry collection mandatory for the migrated scope. Apply the [LangGraph and LangSmith migration plan](ASKTD_LANGGRAPH_AND_LANGSMITH_PLAN.md) for staged delivery, task-level dependencies and acceptance. This supersedes earlier preserve-framework-only wording within that bounded migration. Preserve application behavior and controls, reconcile the team's current work, and record the decision in the operative ADR convention. The complete Master remains proposed; implementation and enterprise/environment qualification remain unverified. [S17]

## What changed in this revision

| Area | Updated position |
|---|---|
| Product focus | A bounded Deposits analytics product, not unrestricted text-to-SQL or autonomous business action. |
| Phase 2F | Preserve lifecycle classification, policy, certified semantics, templates, relationship impact, and bounded hardening as distinct slices. |
| Authorization | Application-enforced user scope plus approved Managed Identity source access; no continuous provider user-ACL synchronization. Enterprise grant authority remains to be confirmed. |
| Semantic ownership | Business/data owners approve meaning; the Registry is the application's single versioned runtime representation. Templates reference definitions rather than duplicate them. |
| Cache | Planned early authorized lookup before avoidable model work, plus separate post-plan reuse. No early-key dependency on `semantic_plan_hash`; no mandatory cache platform. |
| Presentation | Explicit deterministic routing and result validation; AI-assisted formatting is conditional and purpose-approved. |
| Templates | Owners can author parameterized questions and output layouts using approved analyses, with preview, review, versioning, and rollback. |
| Conversation continuity | Separate active-session context, saved history, and explicit personal preferences; reauthorize protected context on every turn. |
| Recurring reporting | Approved saved analyses can become scheduled report subscriptions with secure delivery, recipient checks, freshness rules, and run history. |
| Monitoring and economics | Minimum monitoring and cost evidence start with the pilot. Separate operating cost, cost showback, service subscriptions, and report subscriptions. Formal chargeback requires Finance approval. |
| Delivery | Four proposed product releases, with a readiness period and explicit decision gates; foundational controls are not postponed until late engineering phases. |
| Evidence | Historical source findings, technical test results, planned features, approvals, and runtime activation are recorded separately. |
| Revision 2.1 continuity | Explicit SQL/Databricks baseline, P01–P15 lineage, executive namespace, source availability and the dated session handoff; no new application completion claim. |

---

## 1. Document authority and evidence rules

### 1.1 How to use this plan

Apply the latest explicit owner decision and applicable enterprise approval within its actual scope. Use the September reconciliation for architectural working decisions and the October product documents for the expanded product experience. Preserve earlier implementation reports as dated evidence, not instructions to reset the application. [S02–S11]

This plan does not revoke existing task authority. Equally, a planned feature does not authorize code changes, model calls, new data access, deployment, or feature activation. Resolve any conflicting live task or later master-plan revision before adopting this draft in the application repository.

### 1.2 Evidence labels

| Label | Required meaning |
|---|---|
| **Current / verified** | Directly supported at a named revision and, for operational claims, in a named environment with an observation date. |
| **Technically validated** | Tested in a stated environment; not automatically approved, merged, activated, or released. |
| **Historical baseline** | Supported by an earlier evidence record; not reverified as today's state. |
| **Reported implementation** | Described by a source review, report, or screenshot; not independently rerun for this update. |
| **Observed in PoC** | Demonstrated or stated in a proof of concept; not complete production evidence. |
| **Configured but unused / partial** | Configuration or part of a control exists, without proof that the complete route is active. |
| **Working decision** | Owner direction retained for design, with enterprise qualification identified separately. |
| **Planned / proposed** | Intended delivery, not an implementation claim or unconditional date commitment. |
| **Conditional / future / open** | Dependent on a separate decision, approval, integration, or missing evidence. |

Every operational assertion needs a source revision, environment, date, and relevant evidence. A diagram, source default, successful unit test, or green workflow alone does not prove an active production control.

### 1.3 Preserved access and verification boundary of revision 2.0

Revision 2.0 reviewed the Product Definition and Quarterly Product Roadmap at version 1.1, dated 13 October 2026, and the executive one-pager at version 1.0. Their current package versions preserve this source history. Reviewing planning documents does not verify an application deployment. [S09–S11]

During the 19 October revision 2.0 review, a read of the private application's master-plan path through the configured GitHub connection returned **404**. That does not establish repository deletion, file deletion, or PR status. Accordingly, revision 2.0 used the supplied master-plan screenshots and available reference package; this revision preserves that source basis and it makes no new private-source or runtime verification claim.

Earlier reference copies of `MASTER_PLAN_V1.md` included revision 1.1. They were not substituted for the supplied revision 1.6. The operative application Master and any later candidate require repository reconciliation before replacement.

### 1.4 Traceability

Each delivery item must link its requirement, owner, affected contract, source revision, acceptance tests, release decision, and rollback procedure. Reuse the existing impact report and requirement identifiers rather than creating competing status inventories. Appendix B maps D01–D18 into this plan. [S04, S08]

---

### 1.5 Continuity amendment on 22 October 2026

The 22 October continuity amendment aligns the proposed Master, delivery portfolio, delivery/lineage reference, product documents and handoff. The delivery/lineage reference and Copilot task template were first prepared on 21 October; the amended references remain planning artifacts, not application completion evidence. [S13–S16]

This revision remains a proposed working copy. The currently accessible connection returned 404 for the historically identified application repository on 22 October. No current application HEAD, PR merge, deployment, acceptance or operative Master adoption was verified. A 404 is an access result, not proof of deletion or regression.

The historical application handoff summarized in the [session handoff](ASKTD_SESSION_HANDOFF.md) reports successful normal login and App Service SQL system-assigned managed identity validation. Preserve that dated report and any later evidence. Reopen a completed investigation only when current evidence justifies it. Unreadable screenshot attachments cannot supply missing diagnostic facts. [S15]

Start continuation with the [session handoff](ASKTD_SESSION_HANDOFF.md), then the [delivery and lineage reference](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md). A saved execution prompt is a template, not a new instruction merely because an agent reads it. The operative application documents and existing tasks must be reconciled before generating or implementing new work.

## 2. Executive summary

**AskTD, also referred to as AskAlpha, is an enterprise conversational analytics product. It helps authorized employees ask questions about approved data, understand the answers, and reuse useful analyses.**

The first business focus is Deposits. The product should reduce avoidable reporting effort and make approved analytical questions easier to answer. It complements Power BI and other approved reporting tools; it is not their blanket replacement.

The intended user journey is:

**Ask → Clarify → Analyze → Explain → Explore → Save or Schedule**

Common or high-risk questions should use approved recipes and deterministic presentation. A bounded model-assisted route may support other approved questions, but it must satisfy the same authorization, semantic, query-safety, payload, and answer-integrity controls.

### 2.1 What a useful answer looks like

An illustrative user asks:

> “What was Ontario's month-end deposit balance in September, compared with August?”

The product could answer:

> “September closed at CAD 126 million, up CAD 6 million, or 5%, from August's CAD 120 million.”

The answer shows the approved metric, periods, region, currency, filters, source, and as-of date, followed by a comparison table or approved chart. A follow-up such as “Break that down by product” retains the relevant context and rechecks access.

These figures and names are examples, not approved source data or acceptance results. Business owners must approve the calculation, permitted dimensions, and expected answers before a question becomes supported. [S06, S09]

### 2.2 What is established—and what is not

The supplied records document an accepted foundation through Phase 2E and reported Phase 2F.1 implementation, repair, independent review, and PR publication. They do not establish today's merge, activation, pilot acceptance, or production state. One engineering dataset, one recipe, and 199 evidenced fields do not constitute an approved Deposits business inventory. [S04, S06, S12]

The delivery priority is a narrow, trustworthy end-to-end product before more sources, richer reports, or autonomous capabilities. When capacity is constrained, reduce question coverage or optional channels—not essential access checks, answer validation, monitoring, or cost visibility.

---

## 3. Product scope and boundaries

### 3.1 Product capabilities

All delivery targets below are proposed, not claims of current implementation. [S09–S11]

| Capability | User outcome | Proposed first release |
|---|---|---|
| Governed questions and answers | Ask approved Deposits questions and receive validated answers, tables, and basic charts. | Release 1 |
| Clarification and session follow-ups | Refine the same analysis without repeating every filter; clarify ambiguous requests. | Release 1, bounded scope |
| Feedback and support reference | Report an unhelpful answer and give support a safe correlation reference. | Release 1 |
| Monitoring and initial cost visibility | See reliability, usage, failures, and estimated operating cost. | Release 1 |
| Saved history and questions | Reopen permitted conversations; deliberately rerun an analysis with current data. | Release 2 |
| Explicit preferences | Save, inspect, change, and remove presentation defaults. | Release 2 |
| Owner-created templates | Create reusable question patterns and layouts from approved semantic references. | Release 2 |
| Usage administration | Manage users, enabled capabilities, allowances, and team cost showback. | Release 2 |
| Scheduled reports | Subscribe to an approved analysis; receive a secure link and inspect run history. | Release 3 |
| Contextual suggestions | Find useful next questions and optional preference suggestions. | Release 3 |
| Curated improvement analytics | Help owners identify unmet demand and propose reviewed content improvements. | Release 3 |
| Management reports and approved exports | Combine approved analyses and produce controlled Excel/PDF outputs. | Release 4 |
| Additional data sources beyond the SQL/Databricks baseline | Extend approved analysis through provider-neutral contracts. | Conditional further expansion; baseline provider requirements remain explicit |

Release 1 targets approximately **10–15 common question patterns**, subject to business agreement. The exact question set, personas, metrics, and included follow-up depth must be signed off; the number is not an accepted delivery commitment.

### 3.2 Explicit exclusions

The production-safe core does not include unrestricted SQL over unknown schemas, direct business-data writes, unapproved raw-data retrieval, cross-provider user-ACL replication, autonomous permission or semantic changes, or unreviewed deployment.

Cross-source joins are excluded from the initial multi-source release. Advanced what-if analysis, causal claims, autonomous enterprise actions, automatic model retraining, Genie integration, and additional model providers require separate scope and approval.

No general Graph DB, Redis, SQL Warehouse, serverless compute, SharePoint ingestion, document-crawling VM, or additional channel is made mandatory by this plan. A chosen component must have a justified use, approved contract, owner, and acceptance evidence.

### 3.3 Relationship with Power BI

Power BI or another approved BI tool remains appropriate for regulatory reporting, mandatory scheduled dashboards, pixel-perfect standardized outputs, and formally controlled external distribution.

AskTD serves ad-hoc questions, conversational exploration, approved operational summaries, and report-rationalization opportunities. Its new scheduled-report capability is limited to approved saved AskTD analyses; it does not automatically replace regulatory schedules or formally distributed BI reports. Report type and accountable owner determine the appropriate product.

Power BI integration remains optional unless a separately approved requirement makes it necessary. [S01, S09]

### 3.4 Owner-created question and output templates

A business content owner should be able to create a reusable question without changing application code, **provided the required analysis is already approved**.

For example, an owner creates **Monthly Deposit Movement** with a selectable month, authorized region, optional approved product breakdown, a short summary, a comparison table, and a trend chart. The template references the approved metric and recipe; it does not contain an independent balance formula.

The lifecycle is **Draft → Preview and test → Independent review → Publish a version → Monitor → Revise or retire**. The creator and approver must satisfy the approved maker-checker policy. Owners can roll back or disable a faulty published template without changing the underlying business definition.

A personal saved question simply stores a selection and parameters. It is not a new shared template, semantic approval, or access grant. Section 6 defines the ownership and versioning contracts.

### 3.5 Session context, saved history, and preferences

These are separate capabilities with separate storage, access, and retention rules.

| Capability | Contents | Required behavior |
|---|---|---|
| **Active-session context** | Current metric/recipe references, versions, period, filters, grain, units, relevant result references, and unresolved clarification. | Preserve the current analysis across turns; apply only the requested change; reset unrelated context when topics change. |
| **Saved conversation history** | Permitted messages, analysis context, result references, and the original as-of information. | Reauthorize before display or reuse; distinguish reopening an old answer from rerunning a query. |
| **Personal preferences** | Explicitly saved presentation choices, timezone, display units, and permitted defaults. | User can inspect, edit, delete, or disable them; preferences never override access or approved meaning. |

The application owns conversation state. It must not depend on a model retaining memory between requests. Each new turn resolves current access before loading protected context, updates the structured analysis, clarifies ambiguity, and validates the resulting request.

For “Break that down by product,” retain the earlier month and region only when that reference is unambiguous. For “What about commercial?”, clarify if more than one approved interpretation exists. Concurrent tabs and sessions must not overwrite or mix another analysis's context; the concrete state/versioning mechanism is an implementation decision.

Long conversations may use compact summaries, but those summaries must preserve important dates, filters, units, warnings, and provenance. They remain protected data and cannot be trusted as new instructions or access grants.

Reopening history must not silently rerun model calls or data queries. A separate **Run again** action produces current results, with current authorization and an updated as-of date.

A user can say, “Remember that I prefer a short summary followed by a table.” Repeated choices may later prompt a suggestion, but one question about Ontario is not consent to create a permanent Ontario preference. Preferences must not contain raw customer records or balances.

Explicit request choices override preferences; security and approved semantic rules override both. Retention, deletion, consent, and required audit preservation must be agreed before persistent memory is released. A deleted conversation is removed from conversational reuse without falsely claiming that legally required audit records were erased. [S03, S05, S09]

### 3.6 Scheduled reports and report subscriptions

A user should be able to schedule an approved saved analysis—for example, “Every Monday at 8:00 a.m. Toronto time, prepare the previous week's Deposits summary.”

The schedule records an owner, approved template/recipe versions, parameters, reporting-period rule, timezone, recipients, delivery channel, freshness policy, and status. Users can preview, pause, change, or cancel it. Changes to scope or content require appropriate revalidation.

The initial delivery method is a notification with a **secure report link**. Recheck the owner's permitted scope before execution, recipients' access before delivery, and the viewer's current access when opening the report. One manager's broader permissions must not be used to publish the same unrestricted report to all recipients.

Run history shows scheduled and actual times, data as-of information, content version, outcome, delivery status, and safe correlation reference. Define daylight-saving behavior, retry limits, duplicate prevention, source failure, missed runs, cost limits, and schedule-owner departure before release.

Do not silently substitute stale results or switch to an incompatible template version. Pause, delay, or clearly label an explicitly permitted stale report according to an approved policy. Scheduler and notification technologies remain implementation choices, not new default platform dependencies. [S09–S11]

### 3.7 Suggestions and improvement

Suggestions must reference approved, currently authorized analyses. Showing a suggestion does not execute it or incur an unrequested query. State whether it is related to the current analysis or based on an explicit saved preference.

Owners may inspect aggregated patterns such as repeated unsuccessful questions, frequent clarifications, popular templates, and feedback. Improvement follows **Usage analytics → Offline analysis → Curated proposal → Review → Controlled release**. A monthly standard release is the working cadence, subject to an approved alternative and emergency controls.

Do not let analytics automatically rewrite production templates, infer new KPI definitions, expose other users' questions, or retrain models. [S04, S05, S09]

---

### 3.8 Baseline SQL and Databricks compatibility

Both SQL and Databricks belong to the agreed baseline for Registry bindings, compatible application authorization, execution contracts and readiness. The 21 October owner refinement allocates this work across P01/P02/P04/P05/P07. P15 is for further source, domain or metadata expansion beyond that baseline. [S13, S14]

Keep shared logical definitions and access meaning separate from provider-specific physical objects, dialect, identity/connector configuration, query bounds and result conversion. Common compatibility does not authorize cross-provider joins or establish a qualified live connection.

Qualify each question, provider and environment separately. One qualified route can support an explicitly scoped first pilot while the remaining baseline route is recorded as pending. Do not call that partial activation completion of both providers, and do not postpone mandatory compatibility into optional expansion.

## 4. Architecture and implementation baseline

### 4.1 Dated implementation evidence

This section replaces the old unqualified “verified current” wording with a dated evidence register. [S01, S02, S04, S12]

| Area | Available evidence | What must not be inferred |
|---|---|---|
| React/Vite + FastAPI | The older master records a packaged React frontend served with FastAPI in one Azure App Service boundary. | Today's hosting, network, or deployment identity. |
| Authentication and source identity | Entra/MSAL, backend token validation, and Managed Identity are reported foundations. | Approved enterprise entitlements or fully enabled user-level restrictions. |
| Orchestration | Reported primary deterministic/recipe routes with AG2/`autogen` on relevant model-assisted paths. | A migration to Bottlenose/LangGraph because a target drawing names it. |
| SQL safety | Existing AST/object-scope validation and read-only controls are reported. | That every route, missing-scope case, or deployed flag is proven safe. |
| Phase 2E | Historical accepted PR #17; one engineering dataset/recipe and 199 evidenced fields. | Complete Deposits scope or enterprise metadata coverage. |
| Phase 2F.1 | Reported implementation, M1/M2 repair, independent approval, push, and PR #18 review. | Current merge, feature activation, or completion of all Phase 2F. |
| Test baseline | Reported 1,076 passed, 3 skipped, 87.01% total coverage at the reviewed 2F.1 revision. | Tests rerun for this document, business acceptance, or current production safety. |
| Cache | Bounded in-process metadata caching is documented; a permission-resolution cache is separately reported. | An implemented early analytical cache or distributed result cache. |
| Model integration | Two reported Azure OpenAI integration paths; 16 potential invocation paths. | Sixteen calls per question or verified enterprise-gateway routing. |
| Presentation | Some deterministic primitives exist; relevant paths still reportedly use model-generated reports/summaries. | A completed deterministic-default formatting policy. |
| Diagnostics | Application/debug traces and partial access diagnostics are reported. | Complete durable user/query/data/export audit or enterprise telemetry ingestion. |
| Databricks execution, enterprise telemetry, broader self-service | Runtime qualification remains unverified here; SQL/Databricks compatibility is now explicit baseline scope, while telemetry/self-service retain their scoped qualification requirements. | Deployed services merely because a requirement, diagram or configuration names them. |

Historical identity anchors, not reset targets:

```text
Phase 2E merge / historical main:
  f283f01b6d615f9fa00debcef959d9c5c86a3224
Phase 2F.1 implementation:
  c1639fc779aaed64e4be9fdd17381e0f293c7f9f
Phase 2F.1 repair / last reported candidate:
  6e37281e61a782ffbe8c8675346144567406dabe
Branch recorded in the review:
  phase2/recipe-lifecycle-classification
```

### 4.2 Stack and service decisions

| Layer | Retained direction | Qualification / expansion boundary |
|---|---|---|
| User interface and API | React/Vite and Python/FastAPI; browser uses protected backend APIs. | Preserve the existing approved boundary; do not split services solely to match a drawing. |
| Orchestration | Owner-selected LangGraph migration for future complex, stateful analytical graphs; preserve source-neutral contracts and working behavior. | Follow the scoped migration plan and current ADR/task reconciliation; measure parity, extensibility and overhead. Selection is not implementation or cutover evidence. |
| Identity | Entra user authentication; application authorization; approved workload identity for sources. | Confirm registration topology, groups, token audiences, grants, networking, and revocation. |
| Semantics | Canonical Registry and approved recipes. | Enterprise metadata sources feed a controlled runtime representation, not competing definitions. |
| Query execution | Preserve the approved SQL route and qualify the required SQL/Databricks adapter scope separately. | Interim and target routes must be named and authorized; no assumed SQL Warehouse or serverless availability. |
| Model access | Approved Azure OpenAI use through the applicable enterprise contract. | Both actual helpers require gateway, identity, payload, schema, and retry qualification. |
| Retrieval | Existing narrow Azure AI Search metadata-grounding path where used. | Not the business-semantic authority or analytical engine; broader document ingestion is conditional. |
| Persistence | Purpose-specific application storage for released capabilities. | History, preferences, schedules, results, telemetry, and source data have different lifecycles; select stores explicitly. |
| Telemetry | LangSmith collection is required for migrated application/agent execution telemetry; audit and usage records retain their own contracts. | Qualify the permitted payload, endpoint, access, retention and failure behavior per environment. Other sinks or mocked export do not complete the LangSmith requirement. Other enterprise telemetry products are not assumed active. |
| Cache and delivery | Bounded eligible reuse; complete-response MVP experience. | Redis, distributed cache, and streaming are separate decisions. |

The older master records SSE endpoints; the later working MVP direction is complete responses. Preserve any existing supported endpoint unless a real compatibility issue requires change. Endpoint existence does not establish a streaming requirement, and neither streaming nor caching requires Redis by implication. [S01, S02]

### 4.3 Working target request flow

This is the target contract, not a claim that every stage is implemented.

```text
Entra sign-in → protected application API
  → validate identity and resolve current effective scope
  → load only permitted session context / approved preferences
  → normalize intent and match an approved question template
  → clarify if the request is incomplete or ambiguous
  → EARLY authorized request / template lookup
       eligible reusable result or final response:
         revalidate access, versions, freshness and output eligibility
         → validated presentation / final-output checks
       miss or ineligible entry:
         → approved recipe or bounded semantic planning
         → validate semantics, dependencies, scope and query safety
         → separate post-plan result lookup, where enabled
         → on miss: bounded read-only execution using approved identity
         → result validation
         → explicit response-formatting / template selection
         → final analytical-fidelity and access checks
  → final business output
  → permitted audit, operational trace and usage records
```

Early reuse avoids only the work its eligible object replaces. A saved recipe may avoid SQL generation but still require a new data query. A cached plan is not a fresh result. A cached result may still require presentation. Only an eligible final-response hit can skip both new analysis and formatting work.

For predefined questions, normalization and template matching should be possible without a model call where feasible. Placement before Semantic Planning alone does not prove a zero-model cache hit if an earlier route still invokes a model. Measure actual calls by route. [S04, S05]

### 4.4 Phase 2F.1 invariants

The reported evaluator classifies **`BROKEN > NOT_APPROVED > REVIEW_REQUIRED > VALID`**, preserves all applicable reasons, and returns immutable results from resolved approval and dependency evidence. It is provider-neutral, classification-only, and default OFF. The existing approved-recipe and authorization gates remain the execution controls.

The M1 repair isolates unexpected lifecycle evaluation/payload/trace failures so they cannot change the existing request. It must not swallow errors from the authoritative recipe gate, authorization, or data execution. The M2 repair evaluates non-executable approval status for every record, including ambiguous multi-record evidence. [S12]

An absent or false `RECIPE_LIFECYCLE_CLASSIFICATION_ENABLED` produces no lifecycle trace. If classification is enabled while required governed metadata is unavailable, a `BROKEN` classification is expected; it is not permission to bypass the existing execution gate.

The reported implementation has no approval expiry, renewal, approver ownership, manual override, or `REVIEW_REQUIRED` warn/block policy. Those decisions belong to 2F.2. Malformed lifecycle-flag values remain strict errors when the helper is called directly, but the repaired orchestration boundary preserves request behavior.

Retain the recorded non-blocking observations: silently discarded lifecycle failures have limited observability, and the current resolver may perform **O(D × M)** work and report snapshot-wide conflicts more broadly than the ideal per-dependency contract. Do not describe the originally proposed **O(M + D log D)** bound or exact conflict locality as achieved. Record optimization and precision work separately before scaling beyond the bounded pilot; do not reopen accepted 2F.1 automatically. [S12]

---

## 5. Enterprise architecture principles

| Principle | Delivery rule |
|---|---|
| Governed before dynamic | Runtime definitions and content have validated identity, versions, provenance, and publication state. |
| Deterministic before generative | Prefer approved recipes and templates for common and high-risk questions. |
| Plan before SQL | New analytical execution uses an inspectable, validated semantic plan or approved equivalent recipe contract. |
| Current access at every boundary | Protect metadata, plans, SQL, model context, history, suggestions, cached outputs, reports, and exports. |
| Fail closed for protected processing | Missing or unresolved access cannot yield protected data. Observational lifecycle failure is not an authorization decision. |
| Read-only business data | Validate read-only SQL, allowed objects, required predicates, bounds, timeout, and cancellation before execution. |
| Stable application boundary | Keep the UI behind the approved API and preserve the existing hosting design unless a justified change is approved. |
| Managed Identity first | Use the approved workload identity; no privilege-expanding credential fallback or unsupported custom authentication. |
| Provider-neutral Core | Isolate source, governance, and execution integrations from canonical semantic contracts. |
| Distinct evidence streams | Correlate audit, execution trace, usage metering, and conversational memory without conflating their content or retention. |
| Security before reuse | Cache only eligible authorized objects; revalidate current access and freshness on retrieval. |
| Bounded work | Limit model calls, retries, review loops, context, queries, returned rows, joins, latency, and cost. |
| Evidence before confidence | Use validation, source, freshness, and reconciliation indicators; no uncalibrated confidence percentage. |
| Governed self-service | Authoring does not imply approval or access; publish, rollback, and emergency disable are explicit controls. |
| Small reversible changes | Preserve accepted behavior outside the authorized slice, with proportionate tests and rollback evidence. |

---

## 6. Metadata, recipes, templates, and ownership

### 6.1 One runtime representation; explicit enterprise owners

| Concern | Authority / role |
|---|---|
| Meaning of a KPI, business term, or approved relationship | Accountable business/data owners. |
| Enterprise business catalog | Collibra or another approved source, within confirmed coverage and interface agreements. |
| Technical object metadata and platform governance | Relevant data platform, including Unity Catalog where applicable. |
| Runtime semantic representation | AskTD Semantic Registry: canonical, validated, versioned inputs used by the application. |
| Approved analytical method | Recipe: governed calculation, parameters, dependencies, and permitted execution contract. |
| Question pattern | Question template: wording, parameters, defaults, and references to approved semantic objects. |
| Presentation | Output template and formatting policy: layout and permitted presentation choices, not independent metric definitions. |
| User data access | Approved enterprise grant process, resolved and enforced by the application. Never inferred from metadata ownership. |

This replaces the overly broad statement that “AskTD owns business meaning.” AskTD owns its runtime representation and associated validation/publication behavior, not unilateral authority to change an enterprise KPI. [S02–S04]

If enterprise APIs are unavailable, a bounded manual intake may be proposed with owner approval, provenance, validation, and controlled publication. Do not assume Collibra–Unity Catalog synchronization exists or require a live enterprise-catalog request for every question.

The Registry must express stable logical definitions with separately qualified SQL and Databricks bindings. Application permissions refer to the compatible logical resource/scope model, with provider-specific enforcement evidence. The Plan allocation and named outputs are recorded in the current delivery/lineage reference. [S13, S14]

### 6.2 Semantic and template versioning

Published objects need stable identifiers, versions, source references, owners, validation and approval records, effective dates, and retirement state as applicable. Existing historical objects are not automatically compliant merely because the target contract lists these fields.

A proposed template contract includes its ID/version, referenced KPI/recipe IDs and versions, Registry revision, parameter schema and allowed defaults, approved output-template ID/version, intended audience, owner, review state, and regression examples. These are requirements for contract design, not declarations of current source fields.

Example reference chain:

```text
Monthly Deposit Movement — question template v2
  → approved month-end balance metric ID + version
  → approved month-on-month recipe ID + version
  → governed dataset / field / relationship references
  → published Registry revision
  → approved summary-and-table output template v1
```

A change from “show a table first” to “show a chart first” belongs to presentation versioning. A change to how balance is calculated belongs to semantic/recipe governance. Publishing a template must never silently redefine the metric.

### 6.3 Recipe compatibility

Compatibility is based on the recipe's actual governed dependencies, not every object in the Registry. Unrelated global Registry changes can cause a conservative cache miss without invalidating the recipe. Missing or changed required evidence has an explicit classification and affected-reference explanation.

The pilot's accepted baseline must remain immutable and must not be recomputed from current values as though they were historical approval. Missing approval data must not be interpreted as expiry when expiry is not represented. Any production warning/blocking policy requires the designated owner decision.

The recorded snapshot-wide conflict limitation in Section 4.4 remains an explicit precision gap; this plan does not claim it has been optimized away.

### 6.4 Joins and relationships

AskTD may answer a question requiring several tables only when the required relationships, join keys, cardinality, grain, temporal rules, filters, and ownership are approved and evidenced.

For example, comparing balances by product may require a balance snapshot joined to an account-to-product mapping. Tests must show that a one-to-many relationship does not double-count balances and that both datasets use compatible reporting dates. Similar field names or a model suggestion are not enough to approve a join.

Phase 2F.5 requires evidenced fields, governed endpoint datasets, and consistent names. Do not introduce a graph database or unrestricted cross-source execution to satisfy that requirement.

### 6.5 Controlled publication

Semantic definitions, recipes, question templates, output templates, formatting policies, and cache-compatibility metadata have separate versions but must be validated together where they reference one another.

A release records the changed assets, impact, test results, approver, effective version, rollback version, and affected subscriptions or saved analyses. Rollback must recheck compatible references and current authorization rather than restoring old permissions. Incompatible scheduled reports pause until reviewed.

A minimal owner template editor can ship before a full Metadata Admin Studio. The historical ambition to onboard at least 500 tables remains a later scale objective to validate—not a prerequisite or committed size for the Deposits pilot.

---

## 7. Security, authorization, and caching

### 7.1 Identity and effective scope

Validate the Entra token at the backend, including the approved issuer, audience, application context, and claim handling. Use stable identifiers and approved group object IDs, not display names or browser-supplied region, role, portfolio, team, or cost-centre values as security authority.

AskTD resolves user scope from an approved enterprise entitlement input. Existing application mappings can support an approved interim arrangement, but their presence does not settle the grant owner, namespace, maintenance process, refresh/revocation policy, or deployed enforcement. [S03]

### 7.2 Source access and row/column restrictions

The working MVP model is:

**Authenticated employee → application-enforced effective scope → validated read-only query → approved Managed Identity → approved source objects.**

Preserve the App Service SQL system-assigned managed identity direction. Qualify the actual Databricks host, connector, token route and native grants independently; this document does not substitute a different principal or assume identical provider configuration. [S03, S13–S15]

The source checks the service identity's permissions. It does not automatically apply the initiating employee's rights. Therefore user-specific scope must be enforced in the approved application/query path before protected retrieval, aggregation, model transmission, or output.

Where data requires row or column restrictions, prove the permitted predicates, views, or supported platform mechanism before enabling it. A shared identity with broad access is not sufficient. Do not fetch unrestricted rows and filter only in the browser or after a model receives them.

Do not build continuous provider user-ACL replication. Per-user delegated execution is a separate future identity decision. Normal enterprise group maintenance and controlled application mapping updates are not prohibited ACL synchronization.

Inspect and reuse existing AST/object-scope checks before proposing replacements. Test missing scope, `not_resolved`, malformed queries, revoked access, and protected feature paths with relevant controls enabled; source defaults alone do not establish safety.

### 7.3 Safe failures

| Condition | Required result |
|---|---|
| User is not permitted | Deny without protected metadata, data, or revealing suggestions. |
| Effective scope cannot be resolved or is unacceptably stale | Fail closed with a safe reason and correlation reference. |
| User is permitted but MSI cannot access the source | Safe service/source-access error; protected internal diagnostics; no broader principal or unrestricted fallback. |
| Required row/column treatment is unavailable | Disable the affected data route rather than query unrestricted data. |
| Source or model produces unsafe/invalid output | Bounded correction or safe stop according to approved policy; do not invent a successful answer. |
| Observational 2F.1 lifecycle operation unexpectedly fails | Preserve the repaired best-effort boundary; existing authoritative execution controls still run. |

Raw provider errors, SQL literals, paths, credentials, and unrestricted results must not reach users or models through error handling. Internal detail is limited by its own redaction, access, and retention policy. Source-access diagnostics are not a reason to undo the intentionally silent 2F.1 lifecycle exception behavior.

### 7.4 Two levels of planned analytical reuse

| Level | Position and purpose | Key requirements |
|---|---|---|
| **Early request / template cache** | After current authorization, intent normalization, and template matching; before avoidable semantic-planning/model work. | Use only pre-plan identity. Never require `semantic_plan_hash`. |
| **Post-plan semantic / result reuse** | Reuse an eligible plan or bounded result once the plan/recipe identity is known. | May include plan hash, recipe/dependency identity, and additional post-plan policy versions. |

Early candidate key dimensions include effective authorization scope, tenant/environment, normalized intent, explicit parameters, question-template ID/version, relevant Registry/policy identity, data-freshness version or bucket, requested output shape, and timezone or resolved period when it affects the answer. Final-response reuse also needs the applicable output-template and presentation-policy identity.

Treat plan reuse, result reuse, final-response reuse, permission-resolution caching, metadata caching, and physical data materialization as different mechanisms. A TTL alone is not a proof of fresh source data or timely permission revocation.

Validate cache ownership, scope, versions, sensitivity, freshness, size limits, expiry, and invalidation before serving an entry. Never cache unrestricted data and filter it after retrieval. A cache miss must not change lifecycle approval status.

**Cache platform: planned / TBD.** Benchmark and approve the selected technology, isolation behavior, invalidation, failure mode, and kill switch before activation. Do not introduce Redis or another platform solely for document alignment.

### 7.5 Large-data boundary

The recorded planning context is approximately **5 TB or more**, with Synapse data in **Dedicated SQL Pools** and Databricks data in a **Data Lake**. These locations are not proof that AskTD has approved access or has tested the corresponding workload. [S07]

Keep filtering, joins, and aggregation on approved query compute. Return bounded authorized results. Do not equate a catalog, workspace, physical lake, and query-serving endpoint. Query versus copy/materialization, freshness, source load, cold/warm latency, concurrency, and cost require explicit evidence.

Cache eligible small results, aggregates, plans, matches, and permitted response payloads—not the source dataset. Metadata-only lifecycle evaluation does not establish whole-product performance at 5 TB.

---

## 8. Audit, model governance, quality, monitoring, and cost

### 8.1 Separate records with shared correlation

| Record stream | Purpose | Boundary |
|---|---|---|
| **User/query/data/export audit** | Explain who initiated an operation, the applied authorization version, accessed object references, action, time, and outcome. | Durable, access-controlled evidence according to the approved audit policy; exports cannot proceed without the required record. |
| **Application/agent/model trace** | Explain observable route selection, semantic versions, transitions, validation, retries, and safe failure reasons. | Not hidden model reasoning, unrestricted prompt/result capture, or a substitute for audit. |
| **Usage metering** | Account for actual model attempts, queries, and released service activity. | Trusted attribution and duplicate-resistant aggregation; estimates and reconciled charges remain distinguishable. |
| **Conversation/product records** | Support session continuity, saved history, preferences, schedules, and feedback. | User-visible lifecycle and privacy controls; not an audit archive or universal raw-payload store. |

Correlate request, session, query, model attempt, report run, and delivery identifiers as appropriate. Each stream has an agreed schema, owner, access policy, retention, failure behavior, and deletion treatment. Do not store full prompts, SQL, results, or exception payloads by default.

LangSmith telemetry collection is mandatory for the migrated scope under the 26 October owner decision; follow the [LangGraph and LangSmith migration plan](ASKTD_LANGGRAPH_AND_LANGSMITH_PLAN.md) §5. Actual collection needs permitted-data and environment qualification, including read-back evidence. An interim local route can support development but cannot close the mandatory integration. AIOBS, ADLS transport, OTel bridges, Event Hubs, an outbox and other monitoring products remain separate choices. Do not add every pictured service. Where event transport is selected, prove replay, idempotency, failure handling and delivery reconciliation. [S17]

### 8.2 LLM inventory and model-use controls

Preserve the reported **16 potential invocation paths across two Azure OpenAI application integration paths**. They group into nine purposes: intent, clarification, semantic mapping, planning, SQL generation, error handling, visualization, answer generation, and answer review. They are not sixteen calls per question or sixteen models. [S05]

The maintained inventory needs stable call IDs, exact source revision, callers/helpers, trigger and skip conditions, flags, approved input categories, output schema, validators, retry limits, provider/deployment references, telemetry, and approval coverage. Recover the existing inventory and update deltas; do not invent missing call sites or repeat a completed audit unnecessarily.

Verify both model helpers against the enterprise gateway contract. SDK usage and a configured endpoint do not establish actual gateway routing or deployment approval.

Keep these qualification items separate:

| Gap | Required evidence |
|---|---|
| Safe database-error payloads | Structured permitted diagnostics; synthetic sentinels checked at both actual outbound model boundaries, including relevant retries. |
| Result-bearing transmission | Purpose-specific authorization, minimized fields/rows/aggregates, treatment, and privacy approval. Query access alone is not permission to send results to a model. |
| History and untrusted content | Current-turn access, session ownership, controlled context assembly, and instruction/data separation. Prompt delimiters alone are not redaction or authorization. |
| Output/schema validation | Typed validation and semantic checks; safe malformed-output behavior. |
| Visualization execution | Approved templates or validated chart specifications preferred; retained generated code requires a demonstrated isolation boundary and resource restrictions. |
| Durable evidence | Permitted correlation and events reach the approved store under tested access/retention rules. |
| Business/model acceptance | SME-approved reference answers, named model/use-case owner, and applicable MRM disposition. |

The proposed 2F.1a error-hardening slice is not automatically authorized or complete. Even if completed, it closes only its bounded error-payload requirement—not the other rows.

The proposed MRM boundary is the approved Deposits question-to-final-answer use case, with its individual model interactions documented inside it. MRM must confirm the boundary and ownership. Reuse valid scoped approvals; do not treat ABP, ARB, PIA, DAC, MRM, and production readiness as one approval.

### 8.3 Explicit formatting and analytical fidelity

The preferred route is **Validated result → Approved deterministic template → Final checks → Business output**.

If no suitable deterministic template exists, AI-assisted formatting is permitted only when the use case, payload, model, and presentation policy are explicitly approved. The LLM must not decide whether it is allowed to take that route. If neither route is eligible, return a supported safe outcome or request clarification—not an unapproved model call.

Regression checks protect numbers, KPI values, signs, units, periods, grain, scope, warnings, source attribution, as-of dates, and material qualifiers. Where AI formatting is enabled, use the same validated analytical result to assess both paths; wording may vary, business meaning may not.

Engineering golden tests are necessary but do not replace Deposits SME-approved calculations and expected answers. Add unseen questions, ambiguous/unsupported cases, negative authorization cases, safe-error fixtures, and reconciliation against a trusted source snapshot. Preserve existing assertions; change an expected result only with a justified, recorded contract change.

### 8.4 Minimum monitoring from Release 1

Operations must be able to see request volume, success and failure outcomes, authorization denials, source/model failures, response-time distributions, available usage/cost estimates, and correlation references. Users need a safe way to report an inaccurate answer.

As features ship, add history/preference access events, template publication/rollback, cache eligibility and freshness, scheduled-run and delivery status, duplicate attempts, budget events, and support trends. Alerts need an owner, actionable runbook, escalation path, and tested recovery/disable procedure.

Agree p50/p95 latency, cold/warm behavior, concurrency, freshness, recovery, availability, and cost targets for each released workload. Do not invent numeric SLOs or imply that a successful workflow measures them. Basic monitoring cannot wait for completion of the entire enterprise observability phase.

### 8.5 Operating cost, service subscriptions, and report subscriptions

| Concept | Meaning and rule |
|---|---|
| **Operating cost** | Hosting, model usage, query compute, storage, telemetry, notifications, licences, and support. Count failures and retries as well as successful requests. |
| **Showback** | Explain usage and estimated/reconciled cost to teams without posting a financial charge. Introduce before formal chargeback. |
| **Service subscription / allowance** | The agreed internal or commercial model for access to product capabilities and usage budgets. It never grants business-data permissions. |
| **Formal chargeback** | Financial allocation requiring complete metering, reconciliation, an approved price/allocation catalog, dispute/adjustment handling, and Finance authorization. |
| **Report subscription** | A user's approved recurring report schedule. It is not a software licence or a financial charge. |

Separate interactive questions, scheduled reports, and background processing. Record actual provider-observed token usage where available, deployment/policy version, attempts, outcome, latency, and trusted organizational attribution. A static path count cannot be used as a per-question price.

Distinguish provider consumption from shared or idle infrastructure cost, and estimated costs from reconciled charges. Missing metering is unknown, not zero. The allocation method, currency, price version, and effective date must be recorded. Measure total cost per correct accepted answer or delivered report without excluding failed work from the numerator.

Administrators can set usage allowances, spending alerts, and approved limit behavior. Before a recurring schedule is saved, show its frequency and, when evidence supports it, estimated run cost. A budget limit may queue work or require review; it must not silently weaken access, change analytical meaning, or substitute an unapproved provider.

No subscription price, fixed percentage saving, payment gateway, billing launch, or funded budget is committed here. The service-funding/chargeback decision should be resolved by Release 2; formal charging remains conditional.

---

## 9. Phased delivery roadmap

### 9.1 Preserve engineering history; separate it from product dates

The supplied master uses Phases **0–7**. Later handoffs use some different broad phase labels, including Phase 3 for provider integration and references to later Phases 7–8. They agree on the detailed **2F.1–2F.6** sequence but do not establish a single reconciled broad numbering scheme. [S01, S04, S07, S08]

Preserve the original master labels below as historical identifiers. Add forward references to the actual repository task IDs before assigning implementation. Do not rename existing branches, PRs, or accepted phases to fit a quarterly slide. Executive phases describe outcomes, not engineering completion.

| Original master phase | Retained scope / delivery treatment |
|---|---|
| **0 — Secure foundation and governance** | Preserve completed login, protected-route, security, test, rollback, and governance evidence. Reconcile outstanding formal closure only; reopen work only for a demonstrated current defect. |
| **1 — IAM, SpruceX, and deployment alignment** | Confirm identity/registration, group behavior, workload grants, networking, environment boundaries, and accountable build/run ownership. |
| **2 — Metadata Registry and semantic foundation** | Preserve accepted foundation work; continue actual 2F slices, provenance, governed definitions, and controlled publication contracts. |
| **3 — Fine-grained authorization, audit, quality, and safe execution** | Existing control verification, missing-scope fixes, required row/column treatment, audit, business evaluation, payload safety, renderer qualification, and cache-isolation contracts. Pull the minimum into pilot acceptance. |
| **4 — SQL Server and Databricks scale** | Source-neutral adapters, selected provider route, identity/dialect parity, timeout/cancellation, freshness, concurrency, and bounded provider-side execution. This is cross-referenced as provider Phase 3 in later handoffs; no automatic renumbering. |
| **5 — Model governance, usage, and observability** | Central model policy, actual-call inventory/metering, trusted attribution, qualified trace integration, showback, and approved later chargeback. Minimum observability and payload evidence precede pilot use. |
| **6 — Governed self-service** | Minimal owner template authoring first; later Metadata Admin Studio, approved bulk/incremental onboarding, semantic preview, maker-checker publication, rollback, drift/impact, and owner notification. The historic 500-table objective is a later capacity target. |
| **7 — Production operations and adoption** | Deployment, SLOs, monitoring, runbooks, backup/recovery, canary/rollback, load/security testing, retention, support, adoption, and cost/value evidence. Required operational controls are delivered with each released capability. |

The Phase 4 provider scope supplies required baseline outputs across P01/P02/P04/P05/P07; P15 covers further expansion. A broad phase label does not postpone necessary pilot controls. [S13, S14]

### 9.2 Detailed Phase 2F sequence

| Slice | Scope | Boundary / next evidence |
|---|---|---|
| **2F.1 — Recipe lifecycle classification** | Preserve the reported pure, immutable, deterministic, trace-only evaluator and M1/M2 repairs. | Verify current acceptance/merge/activation only as needed; do not restart from an August prompt. No new execution policy, cache, provider, or UI requirement. |
| **2F.1a — Proposed bounded error hardening** | Structured safe diagnostics at the two actual model integration boundaries. | First establish existing task authority, current need, and whether later work completed it. Synthetic payload tests; no live-data/model call requirement. |
| **2F.2 — Approval / reapproval policy** | Approval authority, evidence, expiry/renewal if required, acknowledgement, and explicit `REVIEW_REQUIRED` behavior. | Owner decision before policy implementation. Do not infer policy from the classifier or a missing timestamp. |
| **2F.3 — Certified semantic catalog** | Deposits KPIs, glossary, business rules, provenance, owner, version, and recipe references. | Business-approved meaning and intake contract; no mandatory live Collibra integration. |
| **2F.4 — Governed templates** | Question/output references, versions, suggestion provenance, deterministic format selection, and analytical-fidelity contracts. | Keep owner UI, persistence, advanced rendering, and exports in separately bounded tasks. Templates cannot redefine KPIs. |
| **2F.5 — Evidence-backed relationships** | Governed relationship endpoints, join semantics, and impact. | Historical D4–D6 evidence prerequisites: fields, endpoints, and naming. These are not September D04–D06. No guessed joins or Graph DB requirement. |
| **2F.6 — Relevant hardening / additional recipes** | Remaining scoped enforcement, compatibility, precision/performance, and approved recipe expansion. | Reuse existing AST checks; add only missing evidence or justified corrections. Pull blocking pilot controls forward. |
| **2G — Publication forward reference** | Version, validate, publish, roll back, and disable compatible semantic/recipe/template/policy assets. | Label is provisional until mapped to the actual source task; do not invent a completed 2G implementation. |

### 9.3 Product delivery milestones

The product roadmap is **four quarters from the agreed team start**. The calendar below is the executive presentation mapping, not a confirmed deadline: readiness in Q4 2026, followed by four releases during 2027. Move dates if capacity or the agreed start changes, while preserving the sequence. [S10, S11]

| Product milestone | Proposed calendar | What the user receives | Minimum proof |
|---|---|---|---|
| **Readiness** | Q4 2026 | Agreed Deposits questions, personas, owners, reference calculations, source route, and demo scope. | Approval/dependency register, workload assumptions, delivery capacity, and pilot acceptance baseline. |
| **Release 1 — Trusted pilot** | Q1 2027 | Validated answers, tables, basic charts, bounded same-session follow-ups, clarification, feedback, monitoring, and initial costs. | Approved reference answers; enabled-path access and payload checks; supported source route; audit/trace, support, and measurable performance. Without approved data, label it a synthetic demonstration. |
| **Release 2 — Everyday use** | Q2 2027 | Saved chats/questions, explicit preferences, owner-created templates, controlled publication, and team usage allowances. | Reauthorization and retention; user-controlled preferences; governed references and maker-checker versions; no metric/access changes through templates. Early reuse is conditional. |
| **Release 3 — Recurring value** | Q3 2027 | Scheduled reports, secure subscriptions, run history, contextual suggestions, owner improvement analytics, and stronger budget controls. | Owner/recipient/viewer checks, freshness, version compatibility, timezone/retry/duplicate tests, delivery monitoring, and approved preference consent. |
| **Release 4 — Management reporting and controlled expansion** | Q4 2027+ | Multi-section reports, richer approved charts, controlled Excel/PDF exports, operational maturity, and optional source expansion beyond the SQL/Databricks baseline. | Format fidelity, audited export, capacity/recovery/support, reconciled costs, and separate approval for each new source or domain. |

The “+” permits later approved expansion. It does not commit autonomous business actions, unrestricted cross-source joins, Genie, or advanced forecasting.

### 9.4 Executive presentation workstreams

| Workstream | Readiness | Trusted pilot | Everyday use | Recurring value | Reporting and expansion |
|---|---|---|---|---|---|
| **Business Experience** | Questions and personas | Answers and follow-ups | Templates and saved work | Scheduled reports and suggestions | Management reports and exports |
| **Trust, Data & Controls** | Owners, definitions, approvals | Access, payload, reference-answer evidence | Content review, history access, consent | Recipient, freshness, and publication controls | Continuous assurance and new-scope approval |
| **Platform & Operations** | Identity, serving, support design | Health, correlation, metering, alerts | Purpose-specific storage and allowances | Reliable schedules, delivery, budgets | Capacity, recovery, support, reconciliation |
| **Adoption & Value** | Users, manual-effort and cost baseline | Quality, feedback, repeat use | Training and template reuse | Recurring use and delivery value | Benefits against total operating cost |

**Executive Gate 1:** Evidence-ready pilot before wider everyday use.  
**Executive Gate 2:** Repeatable value and operational readiness before broader reporting or domain expansion.

These gates supplement, not replace, feature-specific privacy/access controls and the Broad Beta and production gates below. A Q2 milestone is not automatically a production release.

**Executive scorecard:** Answer Quality · Adoption · Control Readiness · Reliability / Latency · Cost / Value.

Measure correctness against approved calculations, returning users and completed tasks, accepted control evidence, request/report reliability and p95 latency, and total cost against measured benefit. Establish numerical targets and the observation period with the responsible owners; adoption alone does not prove savings.

### 9.5 Four-person delivery structure

The planning assumption is the owner plus three additional contributors; availability and skills still need confirmation. Use four work lanes rather than four isolated subprojects:

| Lane | Main responsibility | Required collaboration |
|---|---|---|
| Product and semantics | Question scope, business examples, Registry/recipe/template ownership, acceptance, and dependency follow-up. | Deposits SMEs, governance, architecture. |
| Backend and integrations | Core contracts, authorization, context/reuse boundaries, source/model adapters, and bounded runtime changes. | Platform/IAM and independent code review. |
| User experience and workflows | Chat, template authoring, history/preferences, reporting controls, and administrative views. | Backend contracts and business usability checks. |
| Quality and operations | Cross-route regressions, source/output reconciliation, payload tests, telemetry, metering, and release evidence. | Operations, security, Finance, and all feature owners. |

Assign one implementation owner and a different reviewer to each change. Coordinate overlapping file edits; do not have multiple agents rewrite the same contract concurrently. Every user-facing slice includes its tests, access rules, monitoring, and support behavior—not only the UI or API.

This is a proposed work allocation, not an assignment of unconfirmed enterprise approval authority. Deliver one complete vertical workflow before splitting into parallel features with unstable shared contracts.

---

### 9.6 Delivery Plans and engineering lineage

P01–P15 are delivery packages. They preserve the engineering namespaces above and add output-level ownership. A Plan may draw from several engineering phases, and one phase may contribute to several Plans. The complete mapping, 46 named outputs, typed dependencies, task schema and acceptance links are in the [Delivery Plans and Master Plan Lineage](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md), version 0.4. [S13]

| Plan | Outcome and main Master anchors | First release contribution |
|---|---|---|
| P01 | Pilot scope/reference answers; §§3.1, 9.3, 10.1 | Readiness/R1 |
| P02 | Application access/source routes; Phases 1/3/4, §7 | R1 and each protected feature |
| P03 | Policy/lifecycle disposition; retained 2F.1 and scoped 2F.2 | R1 disposition; new enforcement conditional |
| P04 | Registry/relationships; Phase 2, 2F.3/2F.5, Phase 4 | R1 selected semantic/source bundle |
| P05 | Validated answers; Phases 3/4, 2F.4 and applicable hardening | R1 |
| P06 | Clarification/session follow-ups; §§3.5, 4.3 and Phase 3 controls | R1 |
| P07 | Monitoring/support/metering/feedback/evidence; Phases 3/5/7, §§8, 10–11 | R1 minimum, expanded with releases |
| P08 | Saved work/history/preferences; §3.5 | R2 |
| P09 | Owner templates/publication; §§3.4, 6.5, 2F.4/provisional 2G, Phase 6 | R2 |
| P10 | Usage/showback/allowances; §8.5, Phase 5 | R2; scheduled-work controls in R3 |
| P11 | Authorized reuse; §7.4 and relevant isolation/provider controls | Conditional on evidence/value |
| P12 | Scheduling and secure delivery; §3.6, §11 | R3 |
| P13 | Suggestions/reviewed improvement; §3.7 and Phase 6 publication | R3 |
| P14 | Management reports/exports; §§3.1, 9.3, 11 | R4 |
| P15 | Further source/metadata expansion; §§3.2, 9.1 Phases 4/6 | Conditional beyond baseline |

For product capabilities without one established legacy subphase, record the explicit Master requirement and unresolved task anchor. Do not invent a phase ID. Keep 2F.1a conditional, 2G provisional and historical D4–D6 separate from September D04–D06.

The executive onepager has its own grouping: **Executive 1 = Readiness/R1; Executive 2 = R2/R3; Executive 3 = R4 and conditional expansion**. These labels do not replace Master Phases 0–7 or the later provider Phase 3 alias. [S11, S16]

Each actionable Task has one canonical identity and accountable Plan, with additional requirements/phases linked. Distinguish `requires_output`, `shares_contract`, acceptance gates and conditional relationships. The earlier portfolio's D relationship label and older output aliases map to the current H vocabulary; preserve actual task IDs and reconcile one-to-many aliases. Creating an issue establishes a planning artifact, not implementation or acceptance.

## 10. Pilot acceptance and Broad Beta release gate

### 10.1 Bounded pilot acceptance

Retain the September A01–A10 acceptance model. All rows below require evidence; none is declared complete by this document. [S06]

| Gate | Required evidence |
|---|---|
| **A01 — Scope and ownership** | Approved questions, metrics, objects, personas, treatment, business/model owner, application owner, and pilot exit authority. |
| **A02 — Effective access** | Positive/negative enabled-path tests across metadata, execution, outputs, and any enabled history/cache/export; unresolved access fails closed. |
| **A03 — Governed source route** | Approved endpoint, compute, identity, objects, treatment, freshness, connectivity, and denial behavior. |
| **A04 — Business correctness** | SME-approved reference calculations and expected outcomes, data snapshot/as-of context, units, grain, tolerances, and reviewers. |
| **A05 — Clarification** | Ambiguous and unsupported requests are handled safely across all enabled routes, including template and recipe fast paths. |
| **A06 — Lifecycle compatibility** | Dependency and approval evidence behaves as approved; 2F.1 remains trace-only unless a separate policy change is accepted. Known limitations are explicit. |
| **A07 — Presentation and payload** | Numeric/semantic fidelity, warnings, source/as-of preservation, and no unapproved model transmission. |
| **A08 — Model and evidence coverage** | Enabled-call inventory, input/output boundaries, current-turn history controls, safe correlation, and durable telemetry or accepted interim evidence; migrated scopes additionally require qualified LangSmith collection under S17, not interim-only completion. |
| **A09 — Operations and value** | Agreed workload, latency/concurrency/freshness, failure behavior, cost measures, manual-effort comparison, and support. |
| **A10 — Scoped approval** | Applicable privacy, data, architecture, security, MRM, pilot, and operational approvals, with conditions and review dates. |

A synthetic-data demonstration is valid engineering progress but not operational pilot acceptance. An unresolved external dependency blocks only the affected route or capability; unrelated authorized work can continue.

### 10.2 Broad Beta with restricted data

Before widening access, revalidate the actual architecture and deployment; approve IAM topology and effective scope; prove required row/column controls; and activate complete audit for released user/query/data/export operations. Export must not occur without the required audit record.

Business golden/unseen/reconciliation thresholds, renderer isolation, bounded retries and budgets, safe trace content, monitoring, runbooks, rollback, and applicable Product/Security/Architecture/Data/QA/Platform/Operations decisions must be evidenced.

Any history, preference, cache, suggestion, subscription, or scheduled-report capability enabled in Beta also needs its own access, consent, retention, freshness, and abuse/failure tests. A feature's absence may reduce scope; it must not be represented as a passed control.

---

## 11. Production release gate

Production acceptance includes the applicable pilot/Beta requirements and the following evidence for the actual released scope:

| Area | Release evidence |
|---|---|
| Ownership and platform | Supported production environment, named application/build/run/support owners, and approved registration/identity architecture. |
| Network and access | Validated private networking, DNS/firewall, workload grants, entitlement input, revocation, and denial behavior. |
| Reliability | Capacity, availability, recovery, backup, canary or controlled rollout, and executable rollback/disable procedures tested to agreed targets. |
| Data and semantics | Owners approve freshness, quality, calculations, relationship scope, publication, and change-impact treatment. |
| Model and privacy | Enabled purposes and payloads are within approval; gateway/model policy, output checks, renderer boundary, and bounded attempts are qualified. |
| Evidence and retention | Audit/trace/usage stores, protected access, retention, compliance monitoring, and delivery failure handling are approved and demonstrated. |
| Reuse and memory | If enabled: cache isolation and invalidation, history reauthorization, preference consent/deletion, topic/session isolation, and current access on reuse. |
| Scheduled delivery | If enabled: owner/recipient/viewer authorization, freshness, retries, duplicate prevention, timezone policy, version change, pause/cancel, and run audit. |
| Export | If enabled: approved content, classification, attribution, audit, and distribution controls. Do not promise revocation of every downloaded offline copy. |
| Economics | Metering and request/aggregate reconciliation; agreed budgets and cost ownership. Formal chargeback only after Finance approval and required financial controls. |
| Event infrastructure | If selected: replay, idempotency, dead-letter handling, reconciliation, and bounded backlog behavior. |
| Acceptance decision | Named go/no-go owners record scope, evidence, exceptions, effective release, monitoring period, and rollback triggers. |

A passing CI workflow, merged PR, model approval, or scheduled date cannot replace this decision. No production readiness is asserted here.

---

## 12. Decisions to preserve

Preserve the accepted and working boundaries below when updating code, diagrams, or delivery materials:

- Keep documentation status separate from private implementation and deployed operation; label illustrative data and every unverified claim.
- Preserve accepted work, current user changes, and later task authority. Historical SHAs and old “next step” instructions are not reset targets.
- Keep the UI behind protected APIs and preserve the supported application boundary. Execute only the bounded owner-selected LangGraph migration under S17 when implementation is authorized; diagram labels do not authorize unrelated framework or hosting changes.
- Use approved Managed Identity source access and application-enforced effective user scope. Do not introduce provider user-ACL synchronization, unsupported authentication, or privilege-expanding fallback.
- Use stable group identifiers and approved entitlement sources. Metadata, templates, preferences, service plans, and model output do not grant access.
- Keep enterprise semantic ownership distinct from the Registry's runtime representation. Templates reference definitions; recipes remain dependency-scoped.
- Keep Phase 2F.1 classification trace-only and default OFF, with the existing execution controls authoritative. Do not invent expiry or `REVIEW_REQUIRED` policy.
- Plan early and post-plan reuse separately. Early keys use pre-plan inputs, cache misses are not lifecycle failures, and source-data volume is not cache capacity.
- Prefer approved deterministic formatting. AI formatting is purpose-approved and cannot change analytical meaning or choose its own permission to execute.
- Keep session context, saved history, and explicit preferences separate. Recheck current access before protected reuse; do not silently save inferred personal preferences.
- Govern template and suggestion improvements through reviewed releases. Scheduled reports automate approved read-only analysis, not business actions.
- Keep source/governance/execution seams provider-neutral. Unity Catalog is not query compute; AI Search is not the analytical engine; Genie remains Future / Evaluation.
- Meter actual calls and attempts once implemented. Keep audit, observable traces, usage, and product memory distinct. Showback precedes formal chargeback.
- Deliver minimum access, payload, business evaluation, monitoring, trace, serving, and support proof before pilot use, even when broader work has a late phase label.
- Preserve Power BI complementarity and separate pilot, Broad Beta, production, privacy, architecture, and model-risk approvals.

Historical review incidents and accepted dispositions remain in their original evidence chain. Do not recreate or delete ignored artifacts, rewrite historical reports, or re-run live-worktree tests to make documentation appear clean. This update requires no application execution.

---

## 13. Open decisions, dependencies, and ownership

### 13.1 Enterprise dependencies

G01–G05 are the five High SpruceX dependencies retained from the September package. Their resolution is **not established by the reviewed material**; obtain current owner evidence rather than assuming either completion or permanent blockage. [S04]

| ID | Decision / dependency | Accountable function to confirm | Closure evidence |
|---|---|---|---|
| **G01** | Enterprise entitlement mechanism | IAM + Architecture + Data Owner | Grant authority, group namespace, effective-scope and revocation contract, enabled-path proof. |
| **G02** | Enterprise metadata integration | Data Governance + catalog owners | Coverage, provenance, mapping, intake/refresh, validation, publication, and failure contract. |
| **G03** | Governed interim/target data route | Data Platform + Data Owner/DAC + Architecture | Approved objects, query versus copy, treatment, freshness, and source-load rules. |
| **G04** | Query-serving performance | Data Platform + Operations | Approved endpoint and measured cold/warm latency, concurrency, reliability, freshness, and cost. |
| **G05** | Runtime identity/connectivity | IAM + SpruceX + Network | Identity, token/grant, DNS/firewall, connectivity, and denial evidence. |
| **G06** | Model/use-case ownership and MRM scope | Business + MRM | Named owner and accepted question-to-answer assessment boundary. |
| **G07** | Application registration, build/run ownership, and funding | Technology leadership + Platform/Operations | Official record, accountable owners, support, and cost centre/funding. |
| **G08** | Business evaluation | Deposits SMEs + QA + Product | Approved questions, calculations, thresholds, reviewers, and cadence. |
| **G09** | Enterprise observability | Enterprise service owner + Engineering | Supported integration, permitted content, retention, access, and durable delivery evidence. |
| **G10** | Pilot-to-production transition | Application owner + relevant authorities | Separate production gates and release decision. |
| **G11** | Diagram/runtime reconciliation | Architecture + Engineering + service owners | Confirm framework, hosting, gateway, telemetry, and optional-component dispositions. |

ABP approval is reported in prior material; its scope and current reference must be recorded. ARB, PIA, DAC, MRM, and production decisions are separate. A presentation template's “complete” label is not evidence for any of them.

### 13.2 Product and operational decisions

| Topic | What must be agreed | Needed before |
|---|---|---|
| Deposits scope | Supported questions, personas, data objects, metrics, required restrictions, reference calculations, and included follow-up depth. | Pilot baseline and acceptance. |
| Content ownership | Template creators, independent approvers, publication rights, supported layouts, and release cadence. | Owner self-service. |
| Conversation memory | Retention, history visibility/deletion, session limits, permitted content, consent, and audit preservation. | Persistent history/preferences. |
| Scheduling | Recipients/channels, report ownership transfer, freshness/stale policy, missed-run/DST behavior, delivery limits, and version upgrades. | Report subscriptions. |
| Formatting/model use | Approved deterministic templates, any eligible AI fallback, result treatment, model gateway, and fidelity criteria. | Each enabled presentation route. |
| Lifecycle policy | Approval authority/evidence, renewal/expiry if required, and warn/block/acknowledgement behavior. | 2F.2 enforcement. |
| Cost and service plans | Price catalog owner, allocation method, reconciliation tolerance, service allowances, budget actions, funding, and chargeback authority. | Applicable showback/charging release. |
| Operations | SLOs, workload envelope, retention, incident/escalation, support, recovery, and kill-switch ownership. | Operational pilot and production. |
| Delivery capacity | Four-person availability, agreed start, external support, dependencies, and milestone commitments. | Calendar commitments. |
| Future scale | Additional sources/domains, onboarding volume, cross-source reasoning, and Genie evaluation criteria. | Any expansion beyond the approved scope. |

A named role in a proposal is not an assigned person. Record the actual owner, decision, date, conditions, and evidence without inventing organizational authority.

---

## 14. Immediate next actions

### 14.1 Reconcile and adopt this plan safely

1. In the existing connected development session, read the applicable repository instructions, current task, latest master plan, ADRs, impact report, and preserved model-call inventory. Record actual branch/HEAD, user changes, accepted progress, merge state, and observed runtime configuration. Do not reset to the historical checkpoint.
2. Compare this draft with any later private master-plan edits. Adopt the compatible updates as a documentation change, retaining forward references and the distinction between reported implementation, working decisions, and proposed delivery.
3. Update the existing D01–D18 impact/traceability record with actual file/symbol/test anchors. Do not infer code completion from the revised prose or duplicate a control that already exists.

### 14.2 Continue the smallest justified engineering work

After reconciling the actual current task and baseline, determine whether the proposed 2F.1a safe-error task is relevant, already authorized, still required, and incomplete. Do not automatically make it the next task solely because an older handoff lists it first. If so, keep it limited to permitted structured diagnostics and synthetic outbound-payload tests across both model helpers. If already completed, reuse valid evidence; if not authorized, propose the bounded change without starting it.

In parallel, resolve 2F.2 policy ownership and define the bounded Deposits semantic/template acceptance examples for 2F.3/2F.4. Preserve the actual detailed sequence and relationship prerequisites. Do not turn new history, scheduling, or UI requirements into additions to the accepted 2F.1 commit.

### 14.3 Prepare team delivery and release evidence

Assign the four work lanes in Section 9.5, one accountable implementation owner per slice, an independent reviewer, and the relevant enterprise decision owners. Maintain a shared board linking product outcomes, engineering tasks, prerequisites, acceptance, and release gates.

Prepare the Release 1 demonstration and business reference set using approved data or clearly labelled synthetic fixtures. Establish the first monitoring, audit, usage/cost, support, and workload evidence alongside the analytical feature—not afterward.

Resolve feature-specific memory, template, scheduling, and cost decisions early enough to support Releases 2–3. Do not delay unrelated authorized work while waiting for a source/platform dependency.

### 14.4 Verification and completion reporting

Documentation-only edits do not require an application rebuild or full test regeneration. For code changes, run focused checks and broaden testing for a concrete risk or existing mandatory gate. Use synthetic fixtures and mocked model boundaries unless live execution is separately authorized.

Where read-only review requires byte preservation, run probes and tests in an explicitly authorized external copy, with the correct application-root identity and isolated outputs. Preserve original evidence and report any incident; do not repair it silently.

A completion report must state actual checkpoint, references read, changed paths, verification performed, remaining target-only capabilities, unresolved owner decisions, and the next smallest task. It must separately identify documentation edits, implemented corrections, reported source findings, and verified runtime evidence.

**This document update itself changes no application code, feature flags, data grants, PR state, deployment, or enterprise approvals.**

---

## Appendix A. Reconciliation with the supplied revision 1.6

| Older wording / omission | Revision 2.0 treatment |
|---|---|
| “Verified current” architecture based on the 4 August audit | Retained as dated historical/source evidence, with current deployment requiring verification. |
| Immediate next action begins with Phase 0 closure | Preserve completed work; reconcile actual 2F.1 and later progress before selecting the next task. |
| AskTD owns business meaning | Business/data owners retain authority; Registry is the application's canonical runtime representation. |
| Source-side user identity/RLS wording may imply delegated execution | Retain application enforcement + approved MSI; required row/column restrictions remain mandatory, but delegated identity and provider ACL replication are not default requirements. |
| Result-cache key requires a semantic-plan hash | Valid for a later cache, not the new early cache. Separate reuse layers and eligibility. |
| 2F described mainly as output experience | Preserve detailed lifecycle-to-policy-to-semantics-to-template-to-relationship sequence. |
| Phase numbering differs across later handoffs | Keep history and add capability/task cross-references; do not renumber accepted work. |
| Model-generated presentation treated as a deterministic target | State the reported implementation gap and require routing, payload, and fidelity qualification. |
| History, preferences, and owner templates underspecified | Add explicit product behavior, contracts, ownership, retention, access checks, and release mapping. |
| Scheduled reporting belongs only to BI | Preserve formal/regulatory BI roles while adding approved AskTD saved-analysis subscriptions. |
| Monitoring and usage mainly appear in later phases | Bring minimum proof into Release 1; retain later enterprise-scale integration. |
| Subscription, showback, and chargeback not clearly separated | Distinguish service plans, report subscriptions, operating cost, informational showback, and Finance-approved charging. |
| At least 500 tables as a self-service delivery expectation | Retain as a later scale objective to qualify, not the initial pilot scope or an unconditional commitment. |
| Manager slide implies completed approvals or autonomous enterprise scope | Use the layout only; retain explicit evidence status, proposed dates, and read-only product boundaries. |

## Appendix B. D01–D18 coverage and delivery mapping

These are planning references, not newly instantiated repository tasks. Exact source anchors remain in the existing impact report and must be reconciled by the connected engineering session.

| Delta | Covered here | Owning capability / evidence |
|---|---|---|
| D01 — Deposits-first MVP | §§2, 3, 10 | Approved bounded pilot and reference answers. |
| D02 — Runtime semantics / enterprise ownership | §6 | 2F.3 semantics, 2F.4 references, provenance. |
| D03 — Authorization/MSI without ACL sync | §7 | Existing authorization work, AUTH gates, safe source errors. |
| D04 — Governed data route versus compute | §§4.2, 7.5, 13 | Provider/serving qualification and G03–G05. |
| D05 — Clarification | §§3.5, 4.3, 10 | All enabled routes, including fast paths. |
| D06 — Bounded conversational context | §3.5 | Release 1 session scope; Release 2 persistent history/preferences. |
| D07 — Lifecycle / recipe compatibility | §§4.4, 6.3, 9.2 | Preserve 2F.1; explicit 2F.2 policy decisions. |
| D08 — Cache before avoidable model work | §§4.3, 7.4 | Planned pre-plan and post-plan reuse contracts. |
| D09 — Deterministic formatting | §§6.2, 8.3 | 2F.4 contracts and qualified presentation. |
| D10 — Pilot evaluation | §§8.3, 10 | A04–A07; SME-approved calculations and route tests. |
| D11 — Enterprise observability | §8.1, §8.4 | Pilot evidence plus qualified enterprise integration. |
| D12 — MRM and call inventory | §8.2 | Existing stable inventory; G06 assessment and owner decision. |
| D13 — Conditional integrations | §§3.2, 4.2, 9.1 | Provider-neutral discovery; no automatic Genie/Collibra dependency. |
| D14 — Operating ownership and economics | §§8.4–8.5, 11, 13 | Support, workload, budgets, showback, later approved chargeback. |
| D15 — Framework and gateway | §§4.2, 8.2; S17 amendment | Preserve historical AG2 evidence; reconcile the owner-selected LangGraph migration and separately qualify relevant model helpers. |
| D16 — Streaming and optional ingestion | §§3.2, 4.2 | Complete-response direction; optional services not mandatory. |
| D17 — Protected API and storage roles | §§4.2–4.3, 8.1 | Backend boundary and purpose-specific stores. |
| D18 — Model payload and history qualification | §§3.5, 8.2–8.3, 14.2 | Separate error, result, history, input, output, renderer, and trace closure. |

## Appendix C. Source register

Package documents are linked locally. S01–S08, S12 and S15 identify historical or operative application evidence that is not bundled; locate the corresponding records during repository reconciliation. Their absence from this package does not establish missing implementation. Preserve current source revisions and accepted successors.

| Ref | Source | Use and limitation |
|---|---|---|
| **S01** | User-supplied screenshots of `docs/plans/MASTER_PLAN_V1.md`, revision 1.6, sections 1–14. | Original structure, historical audit, principles, Phases 0–7, gates, and open questions. Not a fresh private-source audit. |
| **S02** | `askalpha_Solution_Architecture_2026-09-14.md`, v1.0. | Reconciled working architecture, ownership, component roles, target/current distinctions. Historical reference; locate the operative source during repository reconciliation. |
| **S03** | `AskTD_02_Authorization_Decision_Record_2026-09-10.md`, updated 14 September, v0.2. | Application/MSI direction, no ACL sync, unresolved enterprise input, and AUTH requirements. |
| **S04** | `AskTD_03_Architecture_Delta_and_Agent_Handoff_2026-09-10.md`, updated 14 September, v0.3. | D01–D18, phase reconciliation, G01–G11, reported checkpoint, and continuation boundaries. |
| **S05** | `askalpha_LLM_Usage_and_MRM_2026-09-14.md`, v1.0. | Reported 16-path/two-helper inventory, nine purposes, L01–L08 gaps, and proposed MRM boundary. Not the full underlying call-site inventory. |
| **S06** | `AskTD_01_Deposits_MVP_Scope_and_Acceptance_2026-09-10.md`, updated 14 September, v0.2. | Bounded Deposits scope and A01–A10 acceptance. Later October product proposals extend the user-facing roadmap; approval is still required. |
| **S07** | `AskTD_09_Phase_2F_Scope_Discovery_2026-08-26.md`, with September historical notice. | Detailed 2F sequence and 5 TB / Synapse Dedicated SQL Pools / Databricks Data Lake context. Earlier execution/expiry wording is superseded by later trace-only implementation and policy decisions. |
| **S08** | `ARCHITECTURE_DELTA_IMPACT_REPORT.md`, operative 14 September update, U1–U7. | Incremental impact mapping and next-task limits. Its preserved September 1 assessment is historical where superseded. |
| **S09** | [AskAlpha Product Definition](PRODUCT_DEFINITION_EN.md), original reviewed v1.1, 13 October 2026; package v1.2, 22 October 2026. | Product features, owners, templates, context/history/preferences, scheduling, monitoring, and costs; later baseline and continuity clarification preserved. |
| **S10** | [AskAlpha Quarterly Product Roadmap](QUARTERLY_PRODUCT_ROADMAP_EN.md), original reviewed v1.1, 13 October 2026; package v1.2, 22 October 2026. | Four relative delivery quarters and acceptance; dates remain proposed. |
| **S11** | [Executive Roadmap](Roadmap-onepager.md), v1.0, prepared 13 October 2026, with 22 October continuity amendment. | Proposed executive calendar, workstreams, gates, and scorecard. |
| **S12** | Supplied August Phase 2F.1 implementation/repair/independent-review/PR #18 screenshots and reports described in the earlier conversation. | Preserved historical report from revision 2.0; these screenshots were not newly inspected during the 22 October continuity update. No current merge or activation evidence. |
| **S13** | [Delivery Plans and Master Plan Lineage](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md), original v0.3, 21 October 2026; v0.4 continuity amendment, 22 October 2026. | P01–P15, named outputs, full phase mapping, dependency types, task/evidence/release lineage and alias transition. Proposed mapping pending operative-source reconciliation. |
| **S14** | Owner direction on SQL/Databricks baseline, application permissions and preserved system-assigned identity, consolidated in the 21 October planning reference. | Refines delivery allocation; does not establish live provider qualification or replace enterprise grant authority. |
| **S15** | Historical application handoff, summarized in the [Session Handoff](ASKTD_SESSION_HANDOFF.md), 22 October 2026. Original application reports require repository reconciliation. | Reports login/SQL SAMI validation and earlier PR/workflow checkpoints. Read as historical evidence; current application state remains unverified. |
| **S16** | [Session Handoff](ASKTD_SESSION_HANDOFF.md) v1.0 and product/quarterly v1.2/executive continuity updates, 22 October 2026. | Reading order, documentation checkpoint, unresolved evidence, executive namespace and continuation guidance. Does not activate saved execution prompts. |
| **S17** | [LangGraph and LangSmith migration plan](ASKTD_LANGGRAPH_AND_LANGSMITH_PLAN.md), v1.0, 26 October 2026; explicit owner direction. | LangGraph selected for complex-graph extensibility; LangSmith telemetry mandatory. Scoped amendment, with current application adoption/qualification evidence still required. |

During the 19 October revision 2.0 review, the private Master read returned 404. The 22 October revision 2.1 review also could not verify the application repository through the available connection. These are historical access observations, not proof of missing code or failure. Product documents and screenshots do not establish current application state.

## Appendix D. Adoption note for the connected engineering session

**Intended application filename:** retain `docs/plans/MASTER_PLAN_V1.md` relative to the application root, after reconciling the actual repository layout and any later edits. The historical layout included a nested application root; resolve the actual root during repository reconciliation rather than assuming that layout.

This file is a proposed replacement draft, not an already committed private-branch edit. Update the existing master at its actual path; do not create a replacement application, reset a branch, overwrite active user changes, or treat this plan as authorization for broad code changes. Keep the engineering artifact language English.

Before adoption, verify the live source baseline and reference locations. After adoption, confirm section coverage, D01–D18 mapping, phase forward references, proposed/current labels, and cross-document consistency. Report only the documentation or implementation work actually performed.


## Appendix E. Continuation checkpoint and update scope

### E.1 Documentation baseline

The 21 October baseline introduced the [P01–P15 reference](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md) and [Copilot artifact-generation template](ASKTD_COPILOT_ARTIFACT_GENERATION_PROMPT.md). The 22 October continuity update aligns this proposed Master, the [portfolio](AskTD_Delivery_Plans_and_Dependencies.md) and [English guide](AskTD_Product_Guide_and_Delivery_Plan_EN_v0_3.md) with reference v0.4, product/roadmap v1.2 and the [session handoff](ASKTD_SESSION_HANDOFF.md). These are documentation changes; no application completion is implied.

### E.2 Evidence still required

| Question | Known evidence | Next source |
|---|---|---|
| Current application repository/branch/HEAD | Historical identity exists; current connector access returned 404 | Connected application workspace/status report |
| Operative Master and later draft | This is a proposed working copy; a prior handoff mentioned MASTER_PLAN_V2.md | Actual files, tracked/untracked changes, adoption evidence |
| Login and SQL identity | Earlier handoff reports successful validation | Preserve existing report; current revision/environment evidence if regression or qualification needs checking |
| Lifecycle versus Snapshot workflows | Earlier questions and historical run references exist | Current caller/callee definition refs, checkout SHA, artifact and deployment lineage |
| Existing Plan/Task/Project synchronization | Prompt and planning specification exist; execution is not evidenced in this record | Actual issue/Project URLs, sync report and current repository records |
| Provider/release acceptance | Requirements and gates are defined | Scope-specific implementation, qualification and accountable decision evidence |

### E.3 Next bounded activity

Read the current session handoff and operative sources. Reconcile existing work and select one representative analytical workflow. Generate the actual Plan/Task artifact package only when that task is requested in its resolved repository/Project. Preserve user changes and any newer Master candidate. A read of a historical prompt does not authorize its actions. Do not reset to old SHAs or infer today's implementation state from this proposed document.

### E.4 Revision history

| Revision | Scope |
|---|---|
| 2.0 proposed, 19 October 2026 | Consolidated product, architecture, engineering and release planning while preserving earlier evidence |
| 2.1 proposed, 22 October 2026 | Clarified dual-provider baseline, SAMI direction, P01–P15/executive lineage, documentation checkpoint, preserved historical login report and continuation guidance |
| 26 October 2026 scoped amendment to proposed 2.1 | Records owner-selected LangGraph and mandatory LangSmith, with delivery under existing P05/P06/P07 outputs. Does not promote the whole Master or assert implementation. |

