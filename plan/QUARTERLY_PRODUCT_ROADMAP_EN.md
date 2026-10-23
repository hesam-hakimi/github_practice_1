# AskAlpha — Quarterly Product Roadmap

**Version 1.2 | 22 October 2026 | Proposed product plan**

**Planning horizon: 12 months from the agreed team delivery start.**

Companion document: [Product Definition](PRODUCT_DEFINITION_EN.md).

**Continuity update:** This revision retains the four-quarter sequence and product scope of version 1.1, prepared 13 October 2026. Read the [Session Handoff](ASKTD_SESSION_HANDOFF.md) for the verified documentation checkpoint and unresolved runtime state, and the [Delivery Plans and Master Plan Lineage reference, v0.4](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md) for detailed Plan, output and Task relationships.

These are four delivery quarters, not fixed calendar quarters. A four-person team remains a planning assumption requiring confirmation. Preserve valid work from the **Phase 2F.1 checkpoint reported in the 13 October 2026 baseline** and any later accepted work. This document does not establish the current application phase, branch, deployment or completion state.

**The roadmap describes proposed product releases. It does not renumber engineering phases or establish that enterprise dependencies have been resolved.**

The four delivery quarters correspond to releases R1–R4. The separate executive onepager groups Readiness/R1 into Executive Phase 1, R2/R3 into Executive Phase 2, and R4/conditional expansion into Executive Phase 3. These are presentation groupings; retain the Master engineering phase names and P01–P15 delivery Plan identifiers independently.

All examples are illustrative. The underlying metrics, data relationships, calculations, access rules, and acceptance owners must be approved before the examples become supported product features.

## Roadmap at a glance

| Delivery period | Release outcome | Main features available by the end of the period |
|---|---|---|
| **Quarter 1 — Months 1–3** | A trusted Deposits pilot | Approved questions, validated answers, basic charts, limited same-conversation follow-ups, feedback, and initial health and cost monitoring |
| **Quarter 2 — Months 4–6** | A product people can use every day | Saved conversations, explicit preferences, saved questions, owner-created templates, controlled publication, and team usage administration |
| **Quarter 3 — Months 7–9** | Recurring reporting and useful personalization | Scheduled reports, secure delivery, report subscriptions, contextual suggestions, improvement analytics, and stronger budget controls |
| **Quarter 4 — Months 10–12** | Management reporting and controlled expansion | Multi-section reports, approved exports, richer visual exploration, operational maturity, and an optional additional approved data source |

## Quarter 1 — A trusted Deposits pilot

### What users receive

A selected Deposits team can ask approved questions and receive an answer with a table or basic chart, supporting definitions, filters, source, and data freshness.

The initial target is approximately **10–15 common question patterns**, subject to confirmation by the business owner. The pilot includes focused clarification and a small set of follow-ups within the active conversation, such as changing the period or requesting an approved breakdown.

Templates are initially curated with the delivery team. A self-service owner editor is not required for this first release.

**Baseline source support includes both SQL and Databricks.** Registry bindings, compatible application authorization, execution contracts and readiness belong to the early Plan scope across P01/P02/P04/P05/P07. Qualification is recorded separately for each question, provider and environment. One qualified route can support an explicitly scoped pilot while the other route remains pending; the second baseline obligation is not deferred into optional Quarter 4 expansion.

End-user access remains enforced in the application. Preserve the App Service SQL system-assigned managed identity direction and required native workload grants. Qualify the actual Databricks identity/connector route separately. Neither a common access contract nor a successful SQL connection establishes live Databricks readiness or authorizes cross-provider joins.

### Monitoring and cost features

From the pilot’s first day, operations can see request volume, response times, failures, model and query usage where measurable, and estimated operating cost.

Users can report an incorrect or unhelpful answer. Support receives a correlation reference rather than relying on screenshots of internal errors.

### End-of-quarter demonstration

A manager asks for September’s deposit balance compared with August, then requests an approved product breakdown. AskAlpha preserves the analysis context and shows consistent numbers.

The same request from a user without the required access is denied without disclosing protected information.

An administrator can find the request, its outcome, elapsed time, and available cost information.

### Release acceptance

The business owner approves the pilot questions and reference calculations. Access is proven on the enabled path, the selected model payloads are approved, and minimum monitoring and support procedures work.

If real data access is not ready, the deliverable is explicitly a **synthetic-data demonstration**, not an operational pilot.

**Not included:** persistent personal memory, owner self-service, scheduled delivery, or unrestricted multi-source analysis.

## Quarter 2 — Everyday use and owner-created templates

### What users receive

Users can find previous conversations, reopen permitted content, and deliberately rerun an analysis with current data. They can save questions and choose explicit preferences, such as summary length, preferred chart style, or display units.

A new conversation can use those approved preferences without automatically inheriting every filter from an older conversation.

### What content owners receive

A limited template editor lets owners create question patterns and presentation layouts using existing approved metrics and recipes.

Owners can define parameters, choose defaults, preview an answer, test it against a reference, and submit it for review. Published versions can be revised or retired through a controlled process.

New metrics and joins remain outside the template editor.

### Monitoring, subscription, and cost features

Administrators receive team-level usage and cost views, user and feature administration, and agreed usage allowances. The commercial-subscription versus internal-chargeback model should be decided by this stage; payment processing is not assumed.

A narrowly scoped early-reuse capability can be introduced for eligible repeated requests once access, freshness, and invalidation rules are proven. It is an optimization, not a prerequisite for every other Quarter 2 feature.

### End-of-quarter demonstration

A user reopens “Monthly Deposits Review,” chooses **Run again**, and receives a fresh answer using their saved presentation preference.

A content owner creates “Monthly Deposit Movement,” tests it, obtains approval, and publishes it to a selected team.

### Release acceptance

History is isolated by user and reauthorized on access. Preferences are visible and editable. A template publication cannot redefine a metric, grant access, or change validated numbers.

**Not included:** automatic preference inference, production template self-rewriting, or a mandatory new data platform.

## Quarter 3 — Scheduled reports and controlled personalization

### What users receive

Users can subscribe to approved reports and choose the reporting period, schedule, timezone, and permitted recipients.

Reports are initially delivered through a secure link. Users can pause or cancel subscriptions and inspect run history.

Contextual suggestions help users continue an analysis or save a frequently repeated task. Repeated choices may prompt a preference suggestion, but saving it requires confirmation.

### What owners and administrators receive

Content owners can see aggregated demand, unsuccessful question patterns, and feedback that may justify a new template.

Operations receive scheduled-run monitoring, failure alerts, controlled retries, and duplicate-delivery protection.

Cost controls now distinguish interactive use from scheduled and background work. Administrators can manage allowances, spending alerts, and policies for exhausted budgets.

### End-of-quarter demonstration

A manager schedules a weekly Deposits summary for Monday at 8:00 a.m. Toronto time.

AskAlpha produces the report, checks recipient access, sends a secure notification, and records the run. A simulated source outage produces a visible delayed or failed status—not an unlabelled old report.

The manager repeatedly selects a short summary. AskAlpha offers to remember that preference rather than saving it silently.

### Release acceptance

Schedules handle timezone changes, fresh-data requirements, access revocation, retries, and incompatible template updates correctly. Recipients cannot view another user’s broader data scope.

Usage analytics produce proposals for human review, not automatic production changes.

**Not included:** autonomous business actions, unrestricted email attachments, or automatic model retraining.

## Quarter 4 — Management reporting and controlled expansion

### What users receive

Users can combine approved analyses into a management report with multiple sections, related charts, and consistent periods and filters.

Permitted Excel and PDF exports become available with source, data date, and classification information. Interactive exploration expands only along approved relationships.

An additional data source or metadata integration beyond the SQL/Databricks baseline can be introduced through P15 where it provides clear value and its access and semantic requirements are ready. This conditional expansion should not displace completion or qualification of the core Deposits experience.

### What administrators receive

The operating dashboard brings together service health, analytical quality, scheduled delivery, usage, and reconciled costs.

The team demonstrates agreed response-time and concurrency targets, support ownership, incident handling, budget controls, and the procedure for disabling a faulty feature or content version.

Subscription or chargeback reporting becomes sufficiently clear for the organization to understand who uses the service and what drives its cost.

### End-of-quarter demonstration

A manager opens a monthly report containing a balance summary, trend, and product comparison. The numbers match across the chat, report, charts, and approved export.

An administrator traces a delayed report to its source issue and sees the related usage and cost.

### Release acceptance

Reports preserve analytical meaning across every format. Exports contain no unauthorized or hidden data. The service meets agreed operational and cost expectations for the released workload.

Access to an already downloaded file is governed by organizational controls; the product must not promise that it can automatically revoke every offline copy.

**Not included:** advanced forecasting, causal analysis, unrestricted cross-source joins, or a guaranteed Genie integration.

## Delivery priorities and dependencies

The team should complete a usable workflow in a narrow scope while retaining the SQL/Databricks baseline obligations, before expanding to further sources or advanced features.

The existing reference package identifies five major dependencies: enterprise entitlements, metadata integration, governed data access, query-serving performance, and runtime identity/connectivity. Their current resolution must be confirmed by the relevant owners.

This expanded product plan also needs decisions on conversation retention, preference consent, template approvers, report recipients and channels, operating budgets, and subscription or chargeback rules.

If capacity is constrained, reduce the number of question patterns, report layouts, delivery channels, or new sources. **Do not remove access checks, answer validation, essential monitoring, or cost visibility to meet a date.**

The intended progression is:

**A trustworthy answer → a reusable daily workflow → a scheduled reporting service → a supportable management analytics product.**


