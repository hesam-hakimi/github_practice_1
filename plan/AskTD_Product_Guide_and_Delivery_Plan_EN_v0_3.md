# AskTD Product Guide and Delivery Plan

**How the product works and how we will deliver it**  
**Version:** 0.3  
**Document date:** 22 October 2026  
**Status:** Proposed delivery guide; implementation and operational readiness require separate evidence.

AskTD helps authorized users ask business questions and receive answers based on approved definitions and permitted data. This guide explains the user journey, the components behind an answer, and the delivery Plans needed to make the selected capabilities available.

The baseline design must support both the selected SQL database route and Databricks. Business meaning and application access rules remain consistent across those routes; each route has its own source mapping, execution implementation and qualification evidence. [S6]

The delivery proposal starts with one complete analytical workflow and expands from evidence. The seven near-term Plans address the pilot. Eight later Plans describe subsequent capabilities. The Plans describe required outcomes; operational readiness is recorded separately for each capability, provider and environment.

## How to use this guide

New users should read Sections 1–5 first. They explain AskTD with one example and introduce the terminology. Delivery participants should then read Sections 6–11. Sections 12–14 provide acceptance checks, the complete phase crosswalk and current continuation references. This revision completes the lineage explanation while preserving the beginner workflow.

| Sections | Reader question |
|---|---|
| 1–2 | What does AskTD do and how does a question become an answer? |
| 3–5 | What are Registry and Recipe, and how do sources and permissions work? |
| 6–10 | What will be delivered, and which outputs depend on each other? |
| 11–14 | What happens next and what evidence establishes acceptance? |

## 1. Understanding AskTD

AskTD is an analytical application for approved business data. A user describes a question in ordinary language. The application connects that request to governed business definitions, checks access, executes a controlled analysis and presents the result with its context. The initial business focus is Deposits. The product is also called AskAlpha in the product references. [S1, S2]

The user should not need to know table names or write a query. They do need to understand the reported metric, filters, period, units and data date. AskTD can ask a clarification question when the request is incomplete. Its planned data operations are read-only; scheduling a report does not authorize a business transaction or a write to a source. [S2]

### A running example

All figures, regions and definitions in this example are illustrative. They are not approved business definitions or actual bank results.

A permitted user asks:

> What was the month-end deposit balance for Region A in September compared with August?

The example assumes an approved closing-balance definition, Canadian-dollar units, matching reporting dates and permission to see Region A.

| Period or measure | Illustrative result |
|---|---|
| August month-end | CAD 120 million |
| September month-end | CAD 126 million |
| Change | Increase of CAD 6 million, equal to 5% |

The answer also identifies Region A, the metric version, the reporting period, the selected source and when its data was last refreshed. The user can ask, “Break it down by product.” AskTD retains the relevant region and period, verifies that the product relationship is approved, and checks current access again. A request for an unauthorized region must not expose that region’s data.

### Who does what

| Role | Responsibility |
|---|---|
| Business user | Asks questions and checks whether the answer addresses the business need. |
| Business and data owner | Approves metric meaning, reference calculations, permitted source objects and relationships. |
| Access administrator | Maintains application access through the approved grant process. |
| Content owner | Creates question and output templates using approved definitions. |
| Engineering and operations | Implements the controls, qualifies routes, monitors the service and supports incidents. |

A person may hold several roles in a small team. Administrative or content-authoring permission does not automatically grant access to every business dataset.

## 2. From a question to an answer

The sequence below describes the target behavior of an analytical request. Some steps may use an approved existing recipe and need little new planning. Every protected path still follows the applicable access and execution controls. [S1, S4]

### Step 1. Sign in and establish current scope

AskTD validates the user’s sign-in token and resolves what that user may do and which data they may use. Group names or filters supplied by the browser are not sufficient authority. If effective access cannot be established, the protected operation stops.

### Step 2. Understand the request and clarify ambiguity

The application identifies the metric, period, region, grouping and output the user requested, using only permitted context. For “balance,” it may need to ask whether the user means a closing balance or an average. The model cannot decide an unapproved business definition.

### Step 3. Select approved meaning and an allowed source

The Registry supplies valid metric, dataset and relationship references. A recipe supplies the approved method. The application selects an allowed, compatible binding to a qualified source. This produces the analytical plan for this request.

### Step 4. Validate the analysis and execute a bounded query

The query must use permitted objects and fields, required user restrictions and approved relationships. The adapter applies the source’s dialect and connection rules. Read-only restrictions, parameters, result limits, timeouts and cancellation follow the accepted execution contract. Source access uses the approved workload identity.

### Step 5. Check the result and present its context

AskTD checks the returned structure, numbers, units, scope and reporting context. A common result format supports a table, chart or summary without changing the meaning. Any model-assisted step receives only its approved, minimized payload. Provider errors and unrestricted rows are not valid user-facing answers.

### Step 6. Continue the analysis and retain safe evidence

A follow-up applies the intended change to application-owned analysis context and rechecks access. The service records a safe correlation reference, relevant outcomes and measurable usage. Session context, saved history and personal preferences are separate capabilities. Displaying an old conversation does not automatically run a new analytical query.

If the request is ambiguous, AskTD asks a focused question. If access or a required capability is missing, it returns a supported explanation and a safe support reference. It must not invent a result to make the interaction appear successful.

## 3. Registry, recipes and templates

The Registry is the application’s versioned catalog of approved business meaning and its connection to data. It holds definitions or references needed at runtime. Business and data owners remain responsible for approving the meaning. Registering an object does not copy all its data or grant anyone permission to read it. [S1]

| Concept | Meaning in the example |
|---|---|
| Metric | What month-end deposit balance means, including its units, grain and reporting rules. |
| Registry | The catalog connecting that metric to approved datasets, fields, recipes, relationships and versions. |
| Recipe | The approved method for comparing two month-end balances, with controlled inputs and dependencies. |
| Analytical plan | This request’s selected metric, Region A, August and September, grouping, source and permitted scope. |
| Source binding | The explicit mapping from logical definitions to objects and fields in a particular source and environment. |
| Adapter | The component that applies the selected source’s connection, query, validation and result-conversion rules. |
| Question template | A reusable question pattern with allowed parameters and references to an approved analysis. |
| Output template | The arrangement of the summary, table and chart; it preserves the validated numbers and meaning. |

### How the pieces fit together

A question template references an approved recipe and metric version. The recipe points to Registry datasets, fields and relationships. The request supplies permitted parameters. A valid binding and adapter execute the analysis. A published Registry snapshot fixes the versions used by that execution.

A product breakdown may need an approved balance-to-product relationship. Its keys, cardinality, grain and time rules must prevent double-counting. Matching column names alone do not establish a valid join.

Recipe approval governs a reusable method; it does not require a human to approve every ordinary question. Existing execution controls and any new lifecycle policy retain explicit rules. [S1, S5]

## 4. SQL and Databricks in one product

Databricks also executes SQL. In this guide, “SQL route” is shorthand for the project’s selected SQL Server, Azure SQL or other specifically qualified SQL-family endpoint. “Databricks route” means the selected Databricks SQL execution endpoint. The exact products and supported modes must be named in the source qualification; support for one SQL-family product does not establish support for all of them.

The baseline requirement is one logical Registry model and one application access model that work with both provider families. Provider-specific mappings and adapters preserve business meaning while handling technical differences. These are design responsibilities, not a statement that either connection is already qualified. [S6]

### Shared meaning and application policy with separate source routes

| Shared across the product | Specific to each provider |
|---|---|
| Metric meaning, units, grain and reporting period | Data types, precision, date functions and dialect |
| Logical dataset, field and relationship identities | Database or catalog, schema, object and field mappings |
| Application actions and effective user scope | Qualified filters, projections, views and execution controls |
| Version and approval references | Connector, endpoint, identity setup, native grants and network |
| Common result and provenance contract | Error mapping, timeout, cancellation and capacity behavior |

### What each Registry binding must explain

For each supported route, a binding identifies the source and environment, fully qualified objects, field mappings, types, precision, units, grain, time interpretation and freshness. It records the compatible logical definition and binding versions, required relationships and supported operations. Connection profiles are referenced through approved configuration; secret values do not belong in published semantic definitions.

For example, one logical “closing balance” metric may have a qualified SQL mapping and a qualified Databricks mapping. Each must preserve the approved definition. Equal metric names do not make different data grains or update times equivalent. Compatibility testing compares a controlled common fixture or otherwise demonstrably comparable data.

Supporting both providers does not automatically permit a join between them. A relationship within SQL or within Databricks is different from an analysis spanning two execution systems. A cross-provider route requires its own approved semantics, access treatment and execution evidence.

## 5. Application access across both sources

Three questions must be answered separately: Who is the human user? What may that user access? What may the running application retrieve from the source? Sign-in, application authorization and workload connectivity answer those questions respectively. [S4]

### One application policy with qualified enforcement

The application access model should express stable logical resources, permitted operations and the applicable row or dimension scope and column restrictions. An approved grant process maintains those permissions. Source bindings connect the logical resource to its SQL or Databricks implementation. The adapters enforce the same intended scope through mechanisms qualified for their own routes.

For the example, a user may read the approved closing-balance metric for Region A and selected product categories. Changing the provider must not expand that permission. A source binding that cannot enforce the required treatment remains unavailable for that protected analysis. Data must be restricted before protected retrieval or aggregation and before any model receives it.

| Situation | Required behavior on SQL and Databricks |
|---|---|
| User has the required current permission | Return only the permitted analysis and context. |
| User lacks permission or scope is unresolved | Stop protected processing and avoid exposing protected metadata or data. |
| Application identity lacks source access | Return a safe service error and support reference. |
| A required mapping or restriction is unsupported | Stop that route and identify the supported limitation. |
| Permission changes after an earlier answer | Recheck access before new queries or protected reuse. |

### Workload identity and native grants

The selected App Service SQL direction retains system-assigned Managed Identity, with an explicit native database grant to that identity. Managed identity remains the retained workload-identity direction. The actual Databricks identity and authentication route must be qualified separately, including the host, connector, token path, supported versions, appropriate workspace assignment and source privileges. This design direction does not establish a working or qualified Databricks connection. [S1, S6]

Shared application authorization does not require identical connection settings. It also does not replace native database or Unity Catalog grants. A shared workload identity represents the application; it must not be assumed to carry each initiating employee’s restrictions automatically. Provider mechanisms, including SQL session-context behavior, cannot be copied to another provider by assumption. [S1, S4]

The retained design does not require continuous replication of every provider’s user ACL into AskTD. Application enforcement still needs an accountable grant authority, trustworthy inputs and an explicit revocation policy. Protection extends to permitted metadata, model context, follow-ups, history, reused results, reports and exports as those features are enabled. [S4]

## 6. Reading the delivery programme

A delivery Plan organizes project work around one outcome. An analytical plan describes how to answer one user question.

| Level | Purpose |
|---|---|
| Master Plan | Sets product direction, requirements, architectural decisions and release expectations. |
| Engineering phase | Preserves an existing engineering scope and identifier, such as 2F.3. |
| Delivery Plan | Defines a coherent outcome, its boundaries, inputs, acceptance and accountable role. |
| Named output | Identifies the contract, behavior or evidence supplied by a Plan. |
| Task | Defines a bounded implementation, verification or decision action with one canonical identity. |
| Evidence | Supports a claim at a named revision, provider, environment and scope. |
| Release | Accepts selected outputs in a specified environment and operating scope. |

P01–P15 are planning identifiers in this guide. Existing repository Plan and Task identities take precedence when the items are adopted. Historical engineering phases remain intact. Creating an issue, merging code, qualifying a source route and accepting a release are separate outcomes. [S1, S5]

Lineage links a Master requirement and engineering phase to a Plan, named output, Task or PR, evidence and release. The relationship is many-to-many: P04 draws from 2F.3 and 2F.5; 2F.4 contributes to P05 and P09. Keep one canonical Task identity and accountable Plan. [S10]

P01–P07 deliver one pilot workflow through shared contracts. Later Plans remain outlines until scope, priority and prerequisites justify detailed Tasks.

### What a dependency means

A dependency names the output needed by another activity. For example, query execution needs a valid metric and source binding for the selected question; it does not need the whole future catalog. Two Plans can agree a contract and then implement their sides in parallel.

| Relationship | Effect |
|---|---|
| Required output | Blocks the activity that actually needs that definition, decision or result. |
| Shared contract | Requires agreement on an interface or behavior before the two implementations meet. |
| Acceptance condition | Blocks acceptance or activation of the affected capability. |
| Conditional dependency | Applies only when a particular policy, feature or integration is selected. |

## 7. The seven near-term delivery Plans

These Plans retain the existing project foundation and add only work justified by the adopted scope and evidence. SQL and Databricks compatibility is part of P01, P02, P04, P05 and P07; it is not deferred to the optional expansion Plan. [S5, S6]

### P01. Pilot scope and reference answers

**Purpose and scope:** Select the business questions, personas, data objects and supported follow-ups that define the pilot. Begin with one representative complete question, then expand the set. The previous 10–15-question target remains subject to business confirmation.

**Deliverables:** A bounded scope, approved metric definitions, reference calculations and acceptance ownership. A source-coverage statement identifies which selected questions must work on SQL, Databricks or both, and the comparable test data needed to prove each claim.

**Dependencies:** The current Master and existing work must be reconciled. Candidate objects are agreed with P02; business owners define meaning with P04.

**Acceptance:** Each question has a calculation method, period, grain, units, allowed scope and explicit unsupported cases. Tolerances and freshness conditions are agreed where needed. Illustrative figures cannot serve as approved reference results.

**Accountability:** Product and semantics, with business/data owners and quality assurance. Broad domain discovery and fixed dates without capacity evidence are outside this slice.

### P02. Application access and qualified source routes

**Purpose and scope:** Make the selected application permissions enforceable on both SQL and Databricks. Preserve existing login, SQL App Service system-assigned identity work and proven query guards; identify actual gaps before creating new implementation work.

**Deliverables:** A common logical access contract, a mapping from effective user scope to each provider route, and separate identity, native-grant, network and connectivity evidence for SQL and Databricks. The selected enforcement covers applicable objects, rows, columns and actions.

**Dependencies:** P01 personas and selected objects; an approved grant authority and source treatment. P02 and P04 agree the logical resource and binding contract together, then progress in parallel.

**Acceptance:** Equivalent logical permissions retain their intended scope on each provider. Denial, unresolved scope, revocation, missing source grants and concurrent-user isolation have evidence. Switching provider cannot broaden access. An unqualified route cannot silently replace a failed one.

**Accountability:** Backend and integrations with IAM, platform/data owners and quality assurance. Continuous provider user-ACL replication and unrelated identity migrations are excluded.

### P03. Recipe approval and reapproval policy

**Purpose and scope:** Define who approves a recipe, which evidence is valid and what changes require review. Expiry, renewal or warning/blocking rules are introduced only when explicitly selected by the accountable policy owner.

**Deliverables:** A policy decision table, any bounded implementation of selected new behavior, and the accepted lifecycle mode for the consuming release.

**Dependencies:** Existing recipe/classification evidence, accountable policy decisions and semantic dependency identities agreed with P04. Semantic design can proceed while policy decisions are being resolved.

**Acceptance:** Missing evidence is not treated as invented expiry. Unrelated Registry changes do not silently invalidate a recipe. Existing execution controls remain authoritative. The accepted trace-only classification mode can remain for a scoped pilot; full new policy enforcement is not a universal prerequisite.

**Accountability:** Engineering and the content/approval-policy owner. Rebuilding the existing classifier or inventing policy from model judgment is outside this Plan.

### P04. Registry and approved relationships for both providers

**Purpose and scope:** Publish the minimum semantic and recipe bundle required by the selected questions, using a common Registry model with explicit SQL and Databricks bindings. Keep semantic certification and required relationship evidence as distinct delivery slices.

**Deliverables:** Stable logical IDs and versions for metrics, datasets, fields, dimensions and relationships; versioned source/environment mappings; approved recipe references; publication, retirement and rollback compatibility records.

**Dependencies:** P01 definitions and reference results, the P02 resource/access contract and applicable approval decisions. Approved manual metadata intake may support a bounded scope when the enterprise integration is not ready.

**Acceptance:** Each supported binding preserves approved meaning, type/precision, units, grain and time interpretation. Required joins have endpoint, key, cardinality and aggregation evidence. Ambiguous or incompatible mappings stop safely. Multi-provider registration does not authorize cross-provider joins.

**Accountability:** Semantics and engineering with business/data owners and quality assurance. A competing enterprise catalog, guessed relationships and large-scale table onboarding are outside the first slice.

### P05. Validated answers through both execution routes

**Purpose and scope:** Turn an authorized question into a correct bounded answer through the selected SQL or Databricks route. Integrate approved semantics, current access, provider-aware validation and controlled presentation.

**Deliverables:** Qualified adapter behavior and a common result contract carrying metric/version, values, units, grain, period, effective scope, warnings, source/binding provenance and data freshness. Curated question/output templates and route-specific evidence accompany the result.

**Dependencies:** P04 semantic and binding outputs, P02 access/source contract, P01 references and P07 event contract. A new P03 policy is required only for a route that adopts it. Contract design can precede live integration.

**Acceptance:** Each provider uses its proper dialect, parameter handling, types, null/date semantics and execution bounds. Controlled comparable fixtures reconcile with references. Output preserves numbers and context. Unsupported operations, source errors and invalid results fail safely. Model-assisted presentation requires its own approved payload and behavior.

**Accountability:** Backend and user experience engineering with semantics, quality and relevant security/model owners. Full authoring UI, scheduling and a new cache platform are outside this Plan.

### P06. Clarification and session follow-ups

**Purpose and scope:** Let the user refine an active analysis while preserving the intended meaning and current access. Keep metric/recipe versions, period, filters, units, grouping and relevant source/binding references in application-owned context.

**Deliverables:** A bounded context contract, clarification behavior and evidence for follow-ups, topic changes and concurrent-session isolation.

**Dependencies:** P04 semantic identities, P05 analysis/result contract and P02 current-access behavior. User-experience design can proceed before the complete live route is accepted.

**Acceptance:** “By product” retains only the intended context and uses approved relationships. Ambiguity leads to clarification. Access is checked before protected context reuse or model transmission. A topic or source change cannot silently retain incompatible meaning or another user’s scope.

**Accountability:** User experience and backend engineering with product and quality assurance. Persistent history, preferences and schedules are separate later capabilities.

### P07. Monitoring, support and acceptance evidence

**Purpose and scope:** Make the selected pilot observable, supportable and measurable from the first usable workflow. Define safe events and support needs early, then collect evidence from the integrated routes.

**Deliverables:** Separate audit, trace and usage contracts; actual attempts and available cost measurements; support/runbook ownership; provider readiness; and release evidence. `P07.feedback` gives users a safe way to report an inaccurate answer, with permitted answer/run correlation, controlled access and a clear review/support route.

**Dependencies:** Contract design starts with P01/P02. Measurements depend on the actual P05/P06 workflow and environment. Business reference owners and the relevant data, model, privacy and operations decisions remain explicit.

**Acceptance:** Evidence distinguishes designed contracts, implemented code, adapter verification and live environment qualification for SQL and Databricks separately. Operations can trace a safe reference, distinguish denial from source/model failure and measure actual work. Targets are agreed from workload needs.

**Accountability:** Quality and operations with engineering and accountable release owners. A synthetic demonstration, an operational pilot, broad Beta and production retain separate acceptance scopes.

## 8. Dependencies and work that can proceed in parallel

The main dependencies below concern required outputs for the selected pilot scope. A new P03 lifecycle policy applies only when selected. Acceptance evidence is distinct from implementation inputs. Pilot acceptance also requires the relevant P01 reference answers, P02 access qualification, P04 semantic/relationship approval and P05 correctness evidence.

| Consumer | Required output | When it is needed |
|---|---|---|
| P02 and P04 | P01 questions, personas, source coverage and definitions | To qualify the selected access and semantic scope. |
| P02 and P04 | Joint logical-object and policy-binding contract | Before the two implementations are integrated; it is not a completion cycle. |
| P05 | P04 meaning/bindings and P02 access/source contract | For integrated acceptance of each selected route. |
| P05 and P06 | P07 event/correlation contract | For instrumentation integration; domain design can proceed earlier. |
| P06 | P05 analysis/result contract and P02 current access | For protected follow-up integration and acceptance. |
| P07 | Actual route evidence from P02, P05 and P06 | For environment-specific qualification and support acceptance. |
| Pilot acceptance | Reference, semantic, access, correctness and operational evidence | Before describing the selected scope as an accepted operational pilot. |

Business definitions, source/access contracts, relevant lifecycle decisions and safe-event contracts can progress together. P05 and P06 can define their result and context contracts during that work. Shared contracts need explicit ownership before parallel edits.

An unavailable real-data approval blocks the affected real-data route. Authorized synthetic work can still establish the design and implementation behavior. It does not complete live access qualification. Similarly, missing Databricks environment access leaves that route visibly pending while eligible SQL work continues.

## 9. Release outcomes

The following sequence retains the product roadmap’s release goals without assigning new calendar dates. Exact dates require agreed scope and capacity. SQL and Databricks compatibility is a baseline requirement across the early Plans, even if operational activation is staged. [S3, S6]

| Release | User outcome | Main Plans |
|---|---|---|
| R1 | A trusted, bounded Deposits workflow with references, access, follow-ups and support evidence. | Required outputs of P01–P07 |
| R2 | Saved work, owner templates and usage administration. | P08, P09, P10; P11 if justified |
| R3 | Recurring reports, secure delivery and reviewed suggestions. | P12, P13 and required P10 budgets |
| R4 | Management reports and controlled exports. | P14; P15 for approved expansion |

A first accepted SQL-only pilot may be explicitly scoped that way. It does not close the Databricks compatibility requirement. Before claiming dual-provider support, the required contract, adapter and environment evidence must exist for both. Broader Beta and production retain their own scope-specific decisions.

## 10. Plans for subsequent capabilities

The outlines below preserve the longer product direction while keeping task detail close to the next executable work. Each feature carries its own current-access, correctness and operational requirements. [S2, S3, S5]

### P08. Saved work and explicit preferences

Deliver three separable outputs: a saved analysis definition, permitted conversation history, and user-controlled preferences. Use P02 current access, P04/P05 versioned definitions and P06 context where history needs it. Reopening does not rerun analytical queries; rerun is explicit. Saved work records valid source/binding references. Preferences cannot change business meaning or grant data rights. Agree retention and deletion behavior.

### P09. Owner templates and controlled publication

Let content owners create parameterized questions and layouts using approved P04 definitions and P05 result/template contracts. Preview, review, publish, retire and rollback have explicit authority. Templates retain valid semantic and binding references. Minimal curated publication is already part of P04/P05; a complete authoring interface is not an R1 prerequisite. A template cannot redefine a metric or grant access.

### P10. Usage administration and budget controls

Use P07 metering and P02 administrative access to explain usage, estimated cost and agreed allowances. Include failures and retries; unknown measurements are not zero. Distinguish estimates from reconciled provider charges. Scheduled-work limits feed P12. Formal chargeback requires its own Finance decision. A feature subscription never grants permission to business data, and a budget limit cannot weaken access controls.

### P11. Authorized analytical reuse

Introduce reuse only when P07 measurements justify it. P02 current scope and P04/P05 versions, bindings, source identity and freshness determine eligibility. Early reuse uses information available before a new analytical plan; later reuse may use its identity. Specify whether the reused object is a plan, bounded result or final response. Prove isolation, revocation and invalidation. A new cache platform is not assumed.

### P12. Scheduled reports and secure subscriptions

Run an approved saved analysis on a controlled schedule and initially deliver a secure link. Require P08 saved analysis or a qualified equivalent, valid published content, controlled source binding, P02 owner/recipient/viewer access, P07 run/delivery evidence and the required P10 budget policy. Check time zones, daylight-saving changes, freshness, retries, duplicate prevention and owner departure. Full history, preferences, authoring UI and export are not prerequisites.

### P13. Contextual suggestions and reviewed improvement

Use the authorized catalog and P06 context to suggest useful next analyses. Feedback-based improvements use the safe aggregate evidence from `P07.feedback`. Preferences are a dependency only for preference-based suggestions. Displaying a suggestion does not execute another query. Proposed improvements pass through review and publication; usage analytics cannot directly rewrite production definitions or reveal another user’s protected activity.

### P14. Management reports and controlled exports

Combine approved P04/P05 analyses into reports and permitted Excel/PDF outputs. Require P02 export scope, provenance, compatible periods and units, size boundaries and mandatory P07 audit. Numbers and meaning must remain consistent across chat, report and export. Scheduling depends on P12 only when selected. Distribution controls govern downloaded copies; the product cannot promise universal offline revocation.

### P15. Additional source and metadata expansion

Add justified providers, source scopes or enterprise metadata integrations beyond the required SQL and Databricks baseline. Use P02 access and P04/P05 semantic/execution contracts, with source-specific qualification and operational evidence. Expansion is conditional on business value and readiness. This Plan does not own the mandatory baseline compatibility work for SQL and Databricks, and does not automatically authorize cross-provider joins or Genie.

## 11. The next deliberate steps

### Current continuation checkpoint

The [Session Handoff](ASKTD_SESSION_HANDOFF.md) records the documentation checkpoint, historical runtime reports, unresolved current evidence and the next bounded action. The [package index](README.md) identifies the local reading order. Documentation availability does not establish application implementation or deployment. [S11]

The application repository, branch, working changes and intended GitHub Project must be reconciled separately. An earlier handoff reports normal-login and SQL system-assigned identity validation; current runtime behavior remains unverified in the documentation baseline. Preserve that earlier evidence and investigate only a demonstrated gap. This guide does not establish that Plan issues, a Project or runtime changes have been completed. [S11]

### Reconcile the baseline once

Confirm the operative Master revision and later decisions. Map existing Plans, Tasks, PRs and valid evidence to the selected scope. Identify the repository, branch, code revision and ownership of relevant local changes. Classify requirements as satisfied, partial, missing, unknown or superseded. An unknown is a question to resolve, not proof that implementation is absent.

### Select and prove one complete analytical workflow

Choose one approved question with a reference calculation, intended personas, data objects, provider coverage and a bounded follow-up. Define the shared business, access, binding, result, context and event contracts. Preserve existing fixes. Implement only proven gaps and verify only uncertainties that matter to the selected acceptance.

The first execution route can be qualified before the second. Both remain in the baseline coverage register. Use comparable controlled data to prove semantics and policy behavior across adapters, then qualify the actual enabled environments separately. Synthetic or mocked evidence cannot be relabelled as a successful live connection.

### Create a small executable Task set

| Task field | What to record |
|---|---|
| Identity and outcome | Canonical Task ID, accountable Plan and exact named output; reuse existing work. |
| Source lineage | Master revision, section/requirement, engineering namespace and primary/supporting phase references. |
| Scope and release | Included objects/routes, intended release, provider, environment and explicit boundaries. |
| Prerequisites | Named output or external decision, relationship type, condition and activity blocked. |
| Acceptance and evidence | Observable behavior, proportionate verification and actual evidence references. |
| Ownership | One implementation owner and the applicable reviewer or decision owner. |
| Execution context | Repository, branch, source revision, relevant existing issue/PR and working changes. |
| State and questions | Artifact state, work state and evidence maturity separately; unknowns stay explicit. |

For example, a P04 Task can map one approved metric to the selected SQL and Databricks objects and demonstrate that types, grain and dates preserve its meaning. This is a Task pattern; the actual objects, expected values and acceptance owner must come from P01/P02 evidence.

If an exact historical phase is unresolved, retain the actual Master product requirement and mark the phase anchor unresolved. Do not invent a phase number. The full Task contract and current output aliases are in the [Plan and Lineage Reference](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md). Older portfolio aliases map to these outputs; they do not create duplicate Tasks. [S10]

### Prepare GitHub changes and expand from the result

Before publication, classify every item as Create, Update, Link existing, No change or Conflict. Preserve existing IDs, human discussion and status. Record output-specific dependency edges and ensure a repeated import cannot create duplicates. Publishing Plans, running workflows and merging code are distinct actions.

For CI/CD work, distinguish the workflow-definition ref, checked-out source SHA, built artifact and deployed version. Then present the selected workflow’s business and operational evidence, expand question coverage and choose later features from observed needs. A green workflow alone does not establish business or operational acceptance.

## 12. Acceptance of SQL and Databricks compatibility

The checks below are requirements for acceptance, not reported test results. Run the applicable checks for each provider and record its evidence separately. Equivalent outcomes are expected only for equivalent definitions, permitted scope and comparable data. [S1, S4, S6]

| Check | Required evidence on each route |
|---|---|
| Registry resolution | Logical IDs resolve to the correct qualified objects, fields and versions. |
| Meaning and result | Reference calculations preserve units, precision, grain, periods and applicable null/time rules. |
| Allowed user | Only permitted objects, rows, columns and operations contribute to the result. |
| Denied or unresolved access | Protected data and metadata are not exposed through answers, errors or model context. |
| Permission change | Current scope governs new queries and enabled history/reuse/follow-up/report paths. |
| Workload access failure | Missing native grants produce safe failure without broader credentials or raw-source fallback. |
| Unsupported capability | Missing mappings, incompatible dependencies or unapproved joins stop the affected route. |
| Execution bounds | Read-only validation, parameters, result limits, timeout and cancellation behave as agreed. |
| Concurrent isolation | Users and pooled connections cannot inherit another user’s scope or session context. |
| Traceability and support | Evidence records provider, source/binding, relevant versions, code/artifact, environment and safe correlation. |

### A readiness record for each provider

For each of Registry binding, application authorization, adapter behavior, workload connection, business correctness and operational support, keep separate SQL and Databricks records. Each record includes status, evidence reference, source revision, environment, observation date, owner and any remaining condition.

Use precise maturity labels. **Designed** means the contract is agreed. **Implemented** means the required code or configuration exists. **Verified** means the stated tests have evidence. **Qualified** means the named environment and operating scope meet their acceptance conditions. **Unknown** or **blocked** records state the exact missing evidence or decision. These labels do not automatically imply one another.

### Decisions needed before operational use

Check current owner records for entitlement and revocation, data objects and treatment, endpoint and identity, reference calculations, model payloads, monitoring, retention and support. A missing decision blocks its affected capability; unrelated authorized design can continue.

## 13. Master Plan lineage and glossary

The Master keeps engineering Phases 0–7 and detailed 2F references. The P01–P15 identifiers describe delivery outcomes. The tables below preserve the Master scope and propose how each scope contributes to those outcomes. A mapping does not prove implementation or acceptance. The connected engineering session must resolve actual Task and PR anchors. [S1, S10]

### Original Master engineering phases

| Master phase and scope | Delivery relationship |
|---|---|
| 0 — Secure foundation and governance | Retained baseline supporting P02 and P07; reuse valid login, protection, test and rollback evidence. |
| 1 — Identity and deployment alignment | P02; P07 qualification and ownership evidence. Identity, grants, network and environment boundaries remain explicit. |
| 2 — Registry and semantic foundation | P03, P04, P05 and P09; preserve the actual 2F slices and controlled publication scope. |
| 3 — Access, audit, quality and safe execution | P02, P05, P06 and P07; applicable controls also follow each protected later feature. |
| 4 — SQL Server and Databricks scale | Baseline P02, P04, P05 and P07, scoped by P01; P15 covers further approved expansion. |
| 5 — Model governance, usage and observability | P07 and P10, with relevant P05 model boundaries. Minimum pilot controls apply from R1. |
| 6 — Governed self-service | P09, with relevant P04, P13 and P15 publication or administration outputs. |
| 7 — Operations and adoption | P07 and the operating requirements of every released Plan. |

Phase numbers identify engineering scope. They do not postpone required access, monitoring or support until the final phase. Later handoffs sometimes call provider integration Phase 3 while the Master calls it Phase 4; retain both source names until their repository anchors are reconciled. [S10]

### Detailed engineering slices

| Existing slice | Delivery treatment |
|---|---|
| 2F.1 — Classification | Retained trace-only baseline; P03 records the applicable lifecycle disposition. |
| 2F.1a — Proposed error hardening | Conditional P05 work with P07 evidence, only if still necessary and authorized. |
| 2F.2 — Approval policy | P03 decision and selected enforcement; full new enforcement is not a universal pilot prerequisite. |
| 2F.3 — Certified semantics | P04 semantic slice with P01 business inputs, meaning, ownership, versions and provenance. |
| 2F.4 — Governed templates | P05 runtime and output contracts; P09 owner authoring. Keep their Task scopes distinct. |
| 2F.5 — Approved relationships | Distinct P04 relationship slice for the questions that require it; preserve separate evidence. |
| 2F.6 — Relevant hardening | Assign each actual gap to its owning Plan; preserve valid existing guards and repairs. |
| 2G — Publication reference | Provisional label: minimal P04/P05 publication and P09 author workflow, subject to actual repository definition. |

Historical relationship prerequisites D4–D6 and September architecture deltas D04–D06 belong to different source namespaces. Keep their source references with the identifiers. P01, P06, P08, P11, P12, P13 and P14 also have Master product requirements whose exact historical Task placement may remain unresolved; that is recorded rather than replaced with invented phase IDs. [S10]

### Executive roadmap phases

The executive roadmap uses a separate three-phase summary. Its numbers summarize product releases and must not be read as Master engineering phase numbers. [S13]

| Executive roadmap phase | Product release relationship |
|---|---|
| Executive 1 | Readiness and R1 trusted pilot. |
| Executive 2 | R2 everyday use and R3 recurring value. |
| Executive 3 | R4 management reporting and separately approved expansion. |

### One question across several Plans

For the month-end balance example, P01 supplies the business reference. P04 supplies the 2F.3 metric and any required 2F.5 relationship, plus SQL and Databricks bindings. P02 enforces current access; P05 executes and presents the bounded result; P06 qualifies the follow-up; P07 records the applicable acceptance evidence. A single question therefore connects several engineering scopes through named outputs. The full lineage register records the actual Tasks and PRs for those outputs. [S10]

### Glossary

| Term | Plain meaning |
|---|---|
| KPI or metric | A defined business measure, such as an approved balance. |
| Grain | What one record or measure represents, such as one account at one reporting date. |
| Dimension | An approved way to group or filter an analysis, such as region or product. |
| Freshness | How current the source data is; it differs from the date the answer is displayed. |
| Provenance | The source, versions and processing references that explain where a result came from. |
| Fail closed | Stop protected processing when permission or a required protective condition is not established. |
| Correlation reference | A safe identifier connecting a user’s request to its support evidence. |
| Provider | The data platform used for a route, such as the selected SQL system or Databricks. |
| Managed Identity | An Azure-managed workload identity used by the application to authenticate to supported resources. |
| Acceptance evidence | Recorded observations and decisions that demonstrate the stated requirement in a named scope. |

## 14. References and programme basis

The local project references establish the product direction and retained decisions. The owner clarification dated 21 October 2026 makes SQL and Databricks Registry/application-policy compatibility part of the baseline. The provider qualification requirements are stated in Sections 4, 5 and 12 so that this guide can be used without external documentation links. They do not certify the project’s deployed configuration.

| Reference | Local source or retained decision | Basis and use |
|---|---|---|
| S1 | [Master Product and Delivery Plan](<MASTER_PLAN_V1(2).md>) | Revision 2.1 proposed, 22 October 2026, retaining the reviewed revision 2.0 basis of 19 October. Product behavior, architecture, phase scope and acceptance remain subject to reconciliation with the operative application repository. |
| S2 | [AskAlpha Product Definition](PRODUCT_DEFINITION_EN.md) | The guide originally used version 1.1 of 13 October 2026. The local Product Definition and Session Handoff preserve subsequent reconciled updates and their status. |
| S3 | [AskAlpha Quarterly Product Roadmap](QUARTERLY_PRODUCT_ROADMAP_EN.md) | The original version 1.1 of 13 October 2026 supplies the release outcomes. This guide retains the later owner-directed dual-provider baseline and separate executive namespace. |
| S4 | Retained authorization decision `ASKTD-ADR-AUTH-2026-09-10`, version 0.2, updated 14 September 2026 | Application authorization, Managed Identity and enterprise grant authority. The relevant requirements are stated in Section 5 and retained in the local Master; reconcile the operative ADR before implementation. |
| S5 | [AskTD Delivery Plans and Dependencies](AskTD_Delivery_Plans_and_Dependencies.md) | Portfolio originally prepared 20 October 2026. Historical output aliases and provider allocation are reconciled through the current Plan and Lineage Reference. Preserve existing repository Task identities. |
| S6 | Owner direction dated 21 October 2026 | Support SQL and Databricks in the Registry and use a compatible application access model. Retain the App Service SQL system-assigned identity direction; qualify the actual Databricks identity and connector route separately. |
| S10 | [AskTD Plan and Lineage Reference](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md) | Version 0.4, 22 October 2026. Full crosswalk, named outputs, typed dependencies, Task contract and reconciliation rules. |
| S11 | [AskTD Session Handoff](ASKTD_SESSION_HANDOFF.md) | Read first when continuing in a new session. Records the documentation checkpoint, historical runtime reports, unresolved current evidence and next bounded action. |
| S12 | [AskTD Copilot Artifact Generation Prompt](ASKTD_COPILOT_ARTIFACT_GENERATION_PROMPT.md) | Version 0.4. Use after the target application repository and intended Project are resolved. Separates planning publication from implementation and records actual operation outcomes. Reading the prompt does not execute it. |
| S13 | Executive roadmap crosswalk in Section 13, the local [Master](<MASTER_PLAN_V1(2).md>) and [Quarterly Product Roadmap](QUARTERLY_PRODUCT_ROADMAP_EN.md) | Executive Phases 1–3 summarize Readiness/R1, R2/R3 and R4. They remain separate from Master engineering phases. |

Use the [package index](README.md) for the local reading order. Documentation revisions, code revisions, built artifacts and deployed versions remain separate evidence identifiers.
