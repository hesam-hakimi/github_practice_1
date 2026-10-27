# AskTD / AskAlpha — Product and Delivery Roadmap

This directory contains the English product, architecture-to-delivery mapping and execution-planning reference package. It is designed to reside at `docs/roadmap/` in the application repository. All document links are relative to this directory.

**Package edition:** 27 October 2026\
**Planning baseline:** Master revision 2.1 proposed; delivery portfolio v0.2; lineage reference v0.4; product and quarterly roadmap v1.2, with scoped 26 October LangGraph/LangSmith and Sources & Connection Health owner amendments.\
**Adoption status:** Reconcile with the operative application Master, ADRs, existing tasks and any later accepted changes before adopting proposed mappings.

## Start here

1. Read the [Product Definition](PRODUCT_DEFINITION_EN.md) for the intended capabilities and boundaries.
2. Read the [Quarterly Product Roadmap](QUARTERLY_PRODUCT_ROADMAP_EN.md) for the release sequence and acceptance outcomes.
3. Use the [English Product Guide](AskTD_Product_Guide_and_Delivery_Plan_EN_v0_3.md) for a practical explanation of the system and planning model.
4. Read the [Master Plan](<MASTER_PLAN_V1(2).md>), [Delivery Portfolio](AskTD_Delivery_Plans_and_Dependencies.md) and [Plan and Lineage Reference](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md) together for engineering scope, output ownership and dependencies.
5. Review the [Planning Handoff](ASKTD_SESSION_HANDOFF.md) and [Product-to-Plan Coverage Review](AskTD_Product_to_Plan_Coverage_Review_2026-10-23.md) before generating new work.
6. Read the [LangGraph and LangSmith migration plan](ASKTD_LANGGRAPH_AND_LANGSMITH_PLAN.md) for the selected orchestration migration, mandatory telemetry, staged scope and task-level dependencies. Reconcile current team implementation before generating duplicate work.

7. Read the [Sources & Connection Health specification](ASKTD_SOURCE_CONNECTION_HEALTH_UI.md) for the R1 diagnostic interface, P02/P07 ownership, five local task candidates and live-versus-synthetic acceptance.
8. Open the [Interactive Architecture Walkthrough](ASKTD_INTERACTIVE_ARCHITECTURE.html) for the clickable question-to-answer flow, agent interactions, all P01–P15 Plans and the synthetic connection-health interface.
9. To resume the established planning run, explicitly submit the [Planning Synchronization Continuation](ASKTD_PLANNING_SYNC_CONTINUATION_PROMPT.md) in the connected application session. It reuses the existing Project and canonical setup prompt, reconciles the latest amendments and assigns only verified human owners.

## Interactive architecture walkthrough

Download `ASKTD_INTERACTIVE_ARCHITECTURE.html` and open it in a browser. It is one self-contained English HTML file with embedded styles, scripts and reference snapshots; no server, installation or external request is required. Keep it beside these documents when copying this package into `docs/roadmap/`.

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
| [New-session Prompt](ASKTD_NEW_SESSION_PROMPT.md) | Read-only restoration of application and planning context. |
| [Project Setup and Task Generation Prompt](AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md) | Canonical template for creating/reconciling Plan and Task issues, dependencies, labels and Project views. |
| [Planning Synchronization Continuation](ASKTD_PLANNING_SYNC_CONTINUATION_PROMPT.md) | Continuation wrapper preserving the reported Project/checkpoint, amendment reconciliation, scoped blockers and verified team allocation. |
| [Artifact-generation Specification](ASKTD_COPILOT_ARTIFACT_GENERATION_PROMPT.md) | Supporting artifact, lineage and synchronization requirements. |
| [Framework Development Continuation](AskTD_Framework_Development_Continuation_2026-10-22.md) | Separate template for explicitly requested bounded framework implementation. |
| [Planning Launcher](prompt) | Short instruction for explicitly starting the Project setup task. |
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

Copy the directory contents intact into `docs/roadmap/`. Compare any existing files and newer Master candidates before replacing them. Preserve active worktrees, staged/unstaged/untracked changes and established task identifiers.

Use the containing application repository and its approved project records to resolve the actual issue repository and GitHub Project. Do not infer an issue destination merely from the location of this documentation. Historical ADRs, runtime records and acceptance evidence identified in the source registers must be reconciled against the application workspace; they are not fabricated by this package.

No document requires an external web link or a personal repository to understand the planning baseline. Source references use local documents, stable document identifiers and revisions. The original filename `MASTER_PLAN_V1(2).md` is retained for compatibility with existing references.

## Execution and evidence boundaries

- Reading or copying a prompt does not execute it. Submit the appropriate task template explicitly.
- The new-session prompt is read-only. Planning generation and framework implementation have separate scopes.
- Preserve SQL and Databricks baseline scope across P01/P02/P04/P05/P07; P15 covers further expansion.
- Preserve App Service SQL system-assigned managed identity and application-enforced end-user authorization. Qualify Databricks identity/connector and each provider/environment separately.
- Retain historical successful login/SQL validation. Investigate a current regression only when current evidence supports it.
- Document existence, issue closure, PR merge and passing technical tests are not interchangeable with business acceptance or release qualification.
- Unknown inputs and evidence remain explicit. Do not invent business definitions, owners, dates, approvals or completion.
- LangGraph migration is selected under P05/P06; LangSmith telemetry is required under P07. This scoped owner amendment does not promote the entire proposed Master or prove application/environment readiness. Preserve audit separation, payload controls and source/provider contracts.
