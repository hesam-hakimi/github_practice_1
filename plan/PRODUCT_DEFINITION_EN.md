# AskAlpha — Product Definition

**Version 1.2 | 22 October 2026 | Proposed product plan**

Companion document: [Quarterly Product Roadmap](QUARTERLY_PRODUCT_ROADMAP_EN.md).

**Continuity update:** This revision retains the product scope and release intent of version 1.1, prepared 13 October 2026. It clarifies the SQL/Databricks baseline and the status of earlier engineering evidence. Read the [Session Handoff](ASKTD_SESSION_HANDOFF.md) for the current documentation checkpoint and unresolved runtime state, and the [Delivery Plans and Master Plan Lineage reference, v0.4](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md) for the engineering-phase, Plan and Task mapping.

## 1. What is AskAlpha?

**AskAlpha is an enterprise analytics assistant that helps employees ask questions about approved business data, understand the answers, and turn recurring analyses into reusable templates and scheduled reports.**

A user should not need to know table names or write SQL. They should be able to ask a question, clarify their intent, explore the result, and see where the numbers came from.

The initial business focus is **Deposits**. Expansion to other business areas will follow once their data, definitions, access rules, and owners are agreed. **Phase 2F.1 was the engineering checkpoint reported in the 13 October 2026 product-planning baseline.** Preserve valid completed work and reconcile the actual application repository, tasks and evidence before assigning a current phase or completion state. The capabilities described below are the target product, not a claim that they are all implemented or deployed.

### A practical example

A deposits manager asks:

> “What was Ontario’s month-end deposit balance in September, and how did it change from August?”

An illustrative answer could be:

> “September’s closing balance was CAD 126 million, compared with CAD 120 million in August—an increase of CAD 6 million, or 5%.”

The answer includes a comparison table, an appropriate chart, the reporting period, the filters used, and the source and freshness of the data.

The manager can then ask:

> “Break that down by product.”

AskAlpha keeps the same region and reporting periods, applies the requested breakdown, and checks that the user is still authorized to see the result.

**All examples and amounts in these documents are illustrative.** The underlying metrics, data relationships, and calculations must be approved before these examples become supported product features.

## 2. Who uses the product?

**Business users** ask everyday questions, compare periods, and investigate changes without writing queries.

**Managers** review concise summaries, save recurring analyses, and receive scheduled reports.

**Business content owners** create question templates and report layouts for their teams, test them, and submit them for publication.

**Data and metric owners** approve the meaning of business terms, calculations, and relationships between datasets.

**Product and operations administrators** manage service availability, usage allowances, costs, support, and the release of approved capabilities.

These responsibilities may be held by fewer people in the pilot, but they remain distinct. Creating a template does not grant permission to redefine a metric or give users additional data access.

## 3. The main user experience

AskAlpha should support a complete analytical workflow:

**Ask a question → clarify anything missing → receive a validated answer → explore the result → save or schedule the analysis.**

Users can start with their own wording or choose an approved question template. When a request is ambiguous, the product asks a focused follow-up question rather than silently choosing an interpretation.

Every analytical answer should make its context visible: metric, period, region or business scope, filters, units, source, and data freshness. Changing the layout must not change the underlying numbers or business meaning.

The target prefers approved, deterministic presentation. AI-assisted formatting is optional and requires approval for the specific information sent to the model. Existing model-generated report paths still need qualification; they must not be presented as an already completed deterministic formatting capability.

### What “follow-up” means

After receiving the September comparison, a user might ask:

> “Show the last six months instead.”

AskAlpha changes the reporting window while keeping the selected metric and authorized region. It displays the updated context before or alongside the answer.

If the user asks, “What about commercial?”, and the term could refer to more than one approved category, the product asks which category they mean.

AskAlpha supports exploration of approved data. It does not invent joins or infer a business cause merely because two values changed together.

## 4. Owners can create their own question templates

**A business content owner should be able to create a reusable question without changing application code, provided it uses an already approved analysis.**

A question template defines what users can ask and which parameters they can change. An output template defines how the answer is presented.

### Example: “Monthly Deposit Movement”

The owner creates a template with the following settings:

| Setting | Example |
|---|---|
| Template name | Monthly Deposit Movement |
| Question pattern | “How did the month-end deposit balance for {region} change in {month}?” |
| User-selectable inputs | Month, authorized region, and approved product category |
| Default period | Previous completed calendar month |
| Approved analysis | Month-end balance compared with the preceding month |
| Output layout | Short summary, comparison table, and trend chart |
| Intended audience | Selected Deposits teams, subject to each user’s data permissions |
| Required information | Currency, filters, reporting period, source, and data freshness |

The owner previews the result using approved test cases, checks it against a reference answer, and submits it for review. Once approved, the template becomes available to its intended audience.

The publication process is:

**Draft → Preview and test → Review → Publish a version → Monitor use → Revise or retire.**

A personal saved question is different: it stores a user’s selected template and parameters. It does not create a new business definition.

### Where the Registry and recipes fit

| Component | What it owns |
|---|---|
| **Semantic Registry** | The application’s versioned representation of approved metrics, business terms, recipes, and data relationships |
| **Recipe** | The approved method for answering an analytical question, including calculations and permitted data dependencies |
| **Question template** | The wording, selectable inputs, defaults, and references to the approved analysis |
| **Output template** | The layout of the summary, table, chart, or report |

For example, a template owner can choose to show a balance in millions and place the comparison chart above the table. They cannot change the definition of “month-end deposit balance” inside that template.

A new calculation or relationship must first pass through the semantic approval process. Templates then reference its approved identifiers and versions.

## 5. Conversation history, session context, and personal preferences

These are three separate product capabilities—not one general “memory” feature.

| Capability | What it remembers | Example |
|---|---|---|
| **Current conversation context** | The analysis being discussed: metric, period, filters, selected breakdown, and unresolved questions | “Break that down by product” keeps the region and month from the previous turn |
| **Saved conversation history** | Previous conversations and the information needed to understand or resume them | Reopen “September Deposits Review” next week |
| **Personal preferences** | User-approved defaults that can apply across conversations | “Use a short summary and show large amounts in millions” |

### How the next response uses the current conversation

Each conversation has its own identifier and a structured analysis context. That context records the selected metric and recipe, their versions, the reporting period, filters, units, relevant result references, and any clarification still required.

For each new message, AskAlpha should:

1. Check the user’s current access.
2. Load the relevant, still-permitted conversation context.
3. Apply the new request, changing only the settings the user intended to change.
4. Ask for clarification when the reference is unclear.
5. Validate the analysis and return the answer with its current context.

The application stores this state; it does not depend on the model remembering a previous request by itself. Only the necessary authorized context is supplied to any model-assisted step.

For long conversations, the product can maintain a compact summary, but that summary must preserve important filters, units, dates, warnings, and references. Switching topics should start a new analysis context rather than carrying unrelated filters forward.

### Reopening an older conversation

A saved conversation should distinguish:

**“This was the answer using data available at that time”** from **“Run this analysis again using current data.”**

Reopening a conversation must not automatically rerun its queries or incur new model and query costs. Rerunning is a separate action.

Access is checked again before showing or reusing protected historical content. If a user’s permissions have changed, an old conversation cannot be used to recover data they can no longer access. This requirement already applies to history and cached-result reuse in the authorization design.

### How personal preferences are saved

Preferences should begin with explicit user choices, such as:

> “Remember that I prefer a short summary followed by a table.”

Repeated behavior can produce a suggestion:

> “You often choose Ontario. Would you like to use it as your default region?”

**One question about Ontario is not enough to establish a permanent preference.**

Users should have a settings page where they can view, change, or remove saved preferences and disable personalization. Preferences may cover presentation style, default reporting period, timezone, and permitted default filters. They should not store raw customer records or balances.

An explicit request overrides a saved preference. Access restrictions and approved business definitions override both.

Deleting a conversation or preference removes it from future conversational reuse. Any audit information that must be retained follows the approved organizational retention policy.

## 6. Suggestions and continuous improvement

AskAlpha should help both the user and the product owner identify useful next steps.

### Suggestions for the user

After a monthly balance comparison, the product might offer:

> “Show the six-month trend”  
> “Compare the approved product categories”  
> “Save this question for next month”

Suggestions must be relevant to the current analysis and available within the user’s current permissions. Displaying a suggestion does not execute another analysis.

Over time, user-approved preferences can influence which suggestions appear first. The product should make the basis understandable—for example, “Related to this analysis” or “Based on your saved display preference.”

### Suggestions for the content owner

Owners should see aggregated information about frequently asked questions, unsuccessful searches, repeated clarifications, and user feedback.

For example:

> “Users repeatedly ask for a regional comparison, but no published template covers it.”

The owner can use that evidence to propose a template or improve an existing one. Changes still require testing and review.

Usage analytics must not directly rewrite production templates, redefine metrics, or retrain models. Improvement remains a controlled release process.

## 7. Scheduled reports and report subscriptions

**Users should be able to turn an approved saved analysis into a recurring report.**

Example:

> “Every Monday at 8:00 a.m. Toronto time, prepare the previous week’s approved Deposits summary and notify me when it is ready.”

The schedule records the question or template version, parameters, reporting-period rule, timezone, recipients, delivery channel, and freshness requirements.

The initial delivery method should be **a notification containing a secure link to the report**. Email attachments and other export methods can follow once their sharing and retention controls are approved.

### Expected behavior

The user can preview the report, create a schedule, pause it, change it, or cancel it. A report history shows the intended run time, actual completion time, data date, delivery status, and safe failure reference.

Before execution and delivery, the product rechecks the schedule owner’s permissions and the recipients’ permitted access. A schedule created by an authorized manager must not become a way to distribute unrestricted data to others.

If a source is unavailable or the data is too old, the report follows an approved policy: delay, stop, or clearly label an allowed stale result. It must not silently present old data as current.

Retries must not create duplicate reports or notifications. A template version change must not silently change the meaning of an existing subscription; incompatible changes require review or pause the affected schedule.

**Creating the ability to schedule reports does not mean AskAlpha can take business actions or write back to source systems.**

## 8. Monitoring, support, and cost management

Monitoring is part of the first usable release, not an enhancement reserved for the end of the roadmap.

### What administrators should see

| Area | Product capability |
|---|---|
| Service health | Availability, errors, source failures, and response times |
| Analytical quality | Reference-answer checks, user-reported inaccuracies, unsupported questions, and presentation inconsistencies |
| Usage | Active users, popular templates, conversation activity, and scheduled-report runs |
| Cost | Model consumption, query execution, storage, monitoring, and shared service costs |
| Report delivery | Completed, delayed, failed, and retried scheduled reports |

Each request and report run should have a correlation reference so support can investigate the relevant events without exposing raw queries, credentials, or unrestricted data.

Alert thresholds, support ownership, and service targets must be agreed before operational use. The existing architecture identifies enterprise monitoring and trace integrations as contracts still requiring qualification—not deployed capabilities.

### Operating costs and subscription costs are different

**Operating cost** is what it costs to run AskAlpha: hosting, model usage, query compute, storage, notifications, monitoring, and support.

**AskAlpha subscription or internal chargeback** is what an organization or team pays—or is allocated—for access to the service. Whether this is an internal cost allocation, a software licence, or a commercial subscription remains a business decision.

The product should support organization-level administration of enabled capabilities, users, usage allowances, and spending limits. A subscription entitlement never grants access to business data.

A practical monthly operating-cost model is:

> **Shared platform and licence costs + model consumption + query execution + storage and telemetry + notification and support costs.**

The cost view should separate interactive questions, scheduled reports, and background processing. Failed attempts and retries still contribute to operating cost and should not disappear from the dashboard.

Estimated usage costs should be clearly distinguished from reconciled provider charges. Shared and idle infrastructure costs need an agreed allocation method.

### Budget controls

Administrators should be able to set spending alerts and usage limits. Before a user creates a recurring report, the product should show its expected run frequency and, when sufficient usage data exists, an estimated cost.

When a limit is reached, the product follows a defined policy: queue work, restrict optional expensive features, or request an increased allowance. It must not silently reduce answer quality or weaken access controls.

No subscription price or cost-saving percentage is committed in this document. Prices require workload measurements and the applicable service agreements. The reported 16 possible model invocation paths are not 16 calls per question and cannot be used as a fixed pricing assumption.

## 9. Product boundaries and acceptance

AskAlpha should remain read-only, use approved analytical definitions, and enforce current access across questions, history, preferences, templates, cached results, reports, and exports.

Its core should remain independent of the selected data provider. Approximately 5 TB is a source-data planning assumption—not a target for caching. Reuse should be limited to eligible, bounded objects.

**SQL and Databricks are both part of the baseline source contract.** The Registry must support approved logical definitions with provider-specific bindings, and application permissions must preserve equivalent access meaning across those bindings. Qualify each provider's execution behavior separately; common semantics do not imply identical schemas, SQL dialects or connection settings. Cross-provider joins are not authorized by this baseline.

End-user permissions remain enforced in the application. Preserve the established App Service SQL system-assigned managed identity direction, alongside the native workload grants required by the source. The actual Databricks identity and connector route must be qualified for its environment; do not silently substitute a different identity design or treat a successful SQL connection as Databricks evidence.

Qualification can proceed in stages for a named question, provider and environment. A scoped pilot may qualify one route first while the other remains explicitly pending; that does not close the other provider's baseline obligation. Additional source or metadata expansion in P15 is beyond this SQL/Databricks baseline. The delivery reference records the associated work across P01, P02, P04, P05 and P07.

A release is usable only when business users can complete its intended workflow and the relevant access, accuracy, privacy, reliability, and support requirements are demonstrated.

Engineering tests are necessary, but they do not replace business-approved reference calculations or acceptance in the intended environment.


