# AskTD / AskAlpha — Product and Delivery Roadmap

This directory contains the English product, architecture-to-delivery mapping and execution-planning reference package. The last connected application report places it at `docs/plans/roadmap/`; the portable staging directory is `plan/`. Earlier `docs/roadmap/` references are an intended/legacy location, not a reason to create another copy. All document links are relative to this directory.

**Package edition:** 30 October 2026\
**Planning baseline:** Master revision 2.1 proposed; delivery portfolio v0.2; lineage reference v0.4; product and quarterly roadmap v1.2, with scoped 26 October LangGraph/LangSmith and Sources & Connection Health owner amendments.\
**Adoption status:** Reconcile with the operative application Master, ADRs, existing tasks and any later accepted changes before adopting proposed mappings.

## Start here

1. Read the [current handoff](ASKTD_SESSION_HANDOFF.md), starting at the 30 October checkpoint. GitHub Projects and Jira synchronization are paused; current planning work concerns the Excel operational view.
2. Use the [new-session prompt](ASKTD_NEW_SESSION_PROMPT.md) for the complete ordered reading protocol. It resolves the current revision, requires full/partial/unavailable read receipts with extracted decisions and creates a working-context checkpoint. It does not promise permanent model memory.
3. Read the product, roadmap, lineage, proposed Master, portfolio, guide, coverage review, executive roadmap and both amendments in that protocol. Reconcile operative application decisions and maintained reports independently.
4. For workbook continuation, read [Excel Delivery Control and Coverage Reconciliation](ASKTD_EXCEL_DELIVERY_CONTROL_REFERENCE.md). Preserve all 15 Plans and 46 outputs; the 13 MIG/CONN candidates are a subset. Obtain the actual XLSX before claiming formula, mapping or repair validation.
5. Open the [interactive walkthrough](ASKTD_INTERACTIVE_ARCHITECTURE.html) as optional teaching material, with its declared snapshot and simulations preserved.
6. Treat all setup, synchronization and implementation prompts as inactive references unless the live owner activates that specific scope. The plain-text [launcher](prompt) now starts read-only context restoration. The [sync wrapper](ASKTD_PLANNING_SYNC_CONTINUATION_PROMPT.md) stays paused until explicit resumption for the affected destination.

## Interactive architecture walkthrough

Download `ASKTD_INTERACTIVE_ARCHITECTURE.html` and open it in a browser. It is one self-contained English HTML file with embedded styles, scripts and reference snapshots; no server, installation or external request is required. Keep it beside these documents when reconciling this package into the actual application documentation directory.

The walkthrough includes the 22-node flowchart and 15 predefined question routes, agent call/return and shared-state explanations, the complete 15-Plan/46-output/25-dependency portfolio, eight LangGraph/LangSmith migration candidates, six complex-graph scenarios and ten connection-health fixtures. Select **Architecture & plan → All Plans** for the portfolio and **Connection health** for the diagnostic prototype.

The five embedded source documents match documentation revision `461d7f85006502bb4fdf0fd31574300ce61b7357`. **Sources & integrity** displays their exact text, hashes and recorded review status. The HTML is an explanatory snapshot, not a separate planning authority or an automatically refreshed dashboard. When a source changes, reconcile the teaching interpretation, refresh the embedded source manifest and regenerate the HTML together; do not manually change its displayed Plan counts or promote proposed decisions.

All examples, graph executions, source attempts and connection checks are simulated. This page does not call the application, data providers, models or LangSmith and does not establish deployed functionality, real authorization, provider qualification or release acceptance.

## Document catalogue

| Document | Purpose |
|---|---|
| [Product Definition](PRODUCT_DEFINITION_EN.md) | Product intent, personas, workflows and safety boundaries. |
| [Quarterly Product Roadmap](QUARTERLY_PRODUCT_ROADMAP_EN.md) | R1–R4 outcomes, relative delivery sequence and acceptance. |
| [Master Plan](<MASTER_PLAN_V1(2).md>) | Comprehensive proposed product/engineering/delivery baseline. |
| [Delivery Portfolio](AskTD_Delivery_Plans_and_Dependencies.md) | P01–P15 outcomes, prerequisites, acceptance and sequencing. |
| [Plan and Lineage Reference](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md) | Engineering crosswalk, 46 named outputs, typed dependencies and Task contract. |
| [English Product Guide](AskTD_Product_Guide_and_Delivery_Plan_EN_v0_3.md) | Beginner guide, concepts, delivery explanations and crosswalk. |
| [Executive Roadmap](Roadmap-onepager.md) | Executive Phases 1–3 and proposed calendar presentation; separate from engineering numbering. |
| [Planning Handoff](ASKTD_SESSION_HANDOFF.md) | Preserved decisions, historical evidence, current unknowns and next bounded activity. |
| [Coverage Review](AskTD_Product_to_Plan_Coverage_Review_2026-10-23.md) | 35 grouped coverage checks and proposed acceptance/ownership refinements. |
| [New-session Prompt](ASKTD_NEW_SESSION_PROMPT.md) | Current-revision resolution, ordered full reads, source-read receipt and context checkpoint; read-only by default. |
| [Excel Delivery Control](ASKTD_EXCEL_DELIVERY_CONTROL_REFERENCE.md) | Full-portfolio workbook requirements, 30 October screenshot findings, mapping corrections and validation criteria. |
| [Project Setup and Task Generation Prompt](AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md) | Canonical template for creating/reconciling Plan and Task issues, dependencies, labels and Project views. |
| [Planning Synchronization Continuation](ASKTD_PLANNING_SYNC_CONTINUATION_PROMPT.md) | Continuation wrapper preserving the reported Project/checkpoint, amendment reconciliation, scoped blockers and verified team allocation. |
| [Artifact-generation Specification](ASKTD_COPILOT_ARTIFACT_GENERATION_PROMPT.md) | Supporting artifact, lineage and synchronization requirements. |
| [Framework Development Continuation](AskTD_Framework_Development_Continuation_2026-10-22.md) | Separate template for explicitly requested bounded framework implementation. |
| [Planning Launcher](prompt) | Starts the new-session read-only restoration protocol; does not start tracker synchronization. |
| [LangGraph and LangSmith migration plan](ASKTD_LANGGRAPH_AND_LANGSMITH_PLAN.md) | Owner-selected LangGraph for future complex graphs, required LangSmith collection, existing-output ownership, staged Tasks and acceptance. |
| [Sources & Connection Health specification](ASKTD_SOURCE_CONNECTION_HEALTH_UI.md) | Required source/authentication/health UI, protected diagnostics, scoped dependencies and acceptance. |
| [Interactive Architecture Walkthrough](ASKTD_INTERACTIVE_ARCHITECTURE.html) | Self-contained English teaching page with the complete portfolio, request flow, agent interactions, migration and diagnostic simulations. |
| [Package Manifest](PACKAGE_MANIFEST.md) | Included revisions, editorial treatment and integrity inventory. |

## Planning model

Preserve the lineage:

**Master requirement/revision → engineering phase/slice → delivery Plan → named output → canonical Task/PR → acceptance evidence → release.**

P01–P15 are delivery Plans. Master phases, detailed 2F slices, provisional 2G, executive Phases 1–3 and R1–R4 releases are separate namespaces. A Task has one accountable Plan; contributing requirements, phases, outputs and releases remain traceable references.

Dependencies identify a producer output and the specific consuming activity. H required outputs, C shared contracts, G acceptance gates and O conditional relationships must retain their distinct semantics. Do not infer whole-Plan blocking relationships from contribution diagrams.

The current documented baseline contains 15 Plans and 46 outputs. Coverage-review refinements are proposals; they do not silently change that register or establish implementation status.

## Repository integration

Locate the existing application package, last reported at `docs/plans/roadmap/`. Compare source revisions, digests, existing files and newer Master candidates before reconciling changes. Preserve destination-only reports and accepted local edits; do not blindly replace the directory or create a second copy at the earlier `docs/roadmap/` path. Preserve active worktrees, staged/unstaged/untracked changes and established task identifiers.

Use the containing application repository and its approved project records to resolve the actual issue repository and GitHub Project. Do not infer an issue destination merely from the location of this documentation. Historical ADRs, runtime records and acceptance evidence identified in the source registers must be reconciled against the application workspace; they are not fabricated by this package.

No document requires an external web link or a personal repository to understand the planning baseline. Source references use local documents, stable document identifiers and revisions. The original filename `MASTER_PLAN_V1(2).md` is retained for compatibility with existing references.

## Execution and evidence boundaries

- Reading or copying a prompt does not execute it. Submit the appropriate task template explicitly.
- The new-session prompt is read-only by default; a concurrent explicit task may proceed after its read/reconciliation gate. No permanent-memory claim is supported.
- GitHub Projects and Jira synchronization are paused. Old saved permission sentences do not resume them. Local planning/Excel work and separately authorized code/PR reviews have their own scopes.
- Workbook photographs establish visible defects only. The actual XLSX, mappings, formulas and repair results remain unverified until inspected.
- Preserve SQL and Databricks baseline scope across P01/P02/P04/P05/P07; P15 covers further expansion.
- Preserve App Service SQL system-assigned managed identity and application-enforced end-user authorization. Qualify Databricks identity/connector and each provider/environment separately.
- Retain historical successful login/SQL validation. Investigate a current regression only when current evidence supports it.
- Document existence, issue closure, PR merge and passing technical tests are not interchangeable with business acceptance or release qualification.
- Unknown inputs and evidence remain explicit. Do not invent business definitions, owners, dates, approvals or completion.
- LangGraph migration is selected under P05/P06; LangSmith telemetry is required under P07. This scoped owner amendment does not promote the entire proposed Master or prove application/environment readiness. Preserve audit separation, payload controls and source/provider contracts.
