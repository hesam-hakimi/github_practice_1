# AskTD / AskAlpha — Planning Baseline and Handoff

**Document ID:** ASKTD-SESSION-HANDOFF  
**Baseline revision:** 1.0, 22 October 2026  
**Repository edition:** 23 October 2026  
**Status:** Documentation checkpoint; application implementation, merge, deployment and release acceptance require current evidence.

## 1. Product and planning objective

AskTD, called AskAlpha in the product documents, is a conversational analytics application for approved business data. Deposits is the initial business focus. Users ask a question, clarify its meaning, receive a validated answer and explore the result within their current access. Later releases add saved work, owner templates, recurring reports and controlled exports.

The delivery framework connects Master requirements to bounded Tasks through named outputs and explicit dependencies. It preserves existing application work and provides a basis for assignable engineering tasks and project visibility. It does not authorize a replacement implementation.

The documented baseline defines **15 delivery Plans**, **46 named outputs**, **25 typed dependency records**, **A01–A10** pilot gates and **D01–D18** architecture-delta coverage. These are planning definitions. Their presence does not establish that corresponding runtime capabilities, GitHub issues or acceptance evidence exist.

## 2. Reading order and source authority

| Order | Document | Role |
|---|---|---|
| 1 | [Package index](README.md) and this handoff | Scope, navigation, evidence boundaries and continuation. |
| 2 | [Product Definition](PRODUCT_DEFINITION_EN.md), v1.2 | Product outcomes, personas and feature boundaries. |
| 3 | [Quarterly Product Roadmap](QUARTERLY_PRODUCT_ROADMAP_EN.md), v1.2 | R1–R4 outcomes and acceptance; relative quarters are not fixed commitments. |
| 4 | [Master Plan](<MASTER_PLAN_V1(2).md>), revision 2.1 proposed | Maintained working copy; reconcile with the operative application Master, ADRs and later candidates. |
| 5 | [Delivery Portfolio](AskTD_Delivery_Plans_and_Dependencies.md), v0.2 | Plan outcomes, acceptance and sequencing. |
| 6 | [Plan and Lineage Reference](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md), v0.4 | Crosswalk, named outputs, dependencies, Task schema and evidence/release mapping. |
| 7 | [English Product Guide](AskTD_Product_Guide_and_Delivery_Plan_EN_v0_3.md), v0.3 | Beginner explanation and phase-to-delivery crosswalk. |
| 8 | [Executive Roadmap](Roadmap-onepager.md) | Separate executive Phases 1–3 and a proposed calendar. |
| 9 | [Coverage Review](AskTD_Product_to_Plan_Coverage_Review_2026-10-23.md) | Coverage findings and proposed output/acceptance refinements. |
| 10 | [Project Setup Prompt](AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md) | Current planning/task/Project execution template; submit explicitly when that work is requested. |

Authority depends on scope and adoption, not date alone. Apply accepted enterprise decisions and current explicit project direction within their scope. A proposed working copy must not silently replace the operative application Master or an accepted task. Record conflicts and reconcile their affected scope.

The package is designed to reside under `docs/roadmap/` in the application repository. The folder containing documentation does not itself identify the intended issue repository or GitHub Project. Resolve those targets from the active application workspace and approved project records before synchronization.

## 3. Directly established documentation baseline

The maintained Master, delivery portfolio, English guide, product/roadmap documents and lineage reference form the planning baseline. This repository edition places the related documents together and uses relative references so the folder can be copied intact.

The [coverage review](AskTD_Product_to_Plan_Coverage_Review_2026-10-23.md) found no wholly unowned major product capability in the combined planning documents. It identified refinements needed before reliable task generation: explicit P10 administration ownership, administrator-visible P07 acceptance, P12 frequency/conditional-cost preview, P07/P09/P13 analytics dependencies, and detailed user-visible acceptance clauses.

Those recommendations remain proposed. In particular, `P10.service_administration` is an example proposed output, not an adopted forty-seventh output. Preserve the existing register until an accepted decision changes it.

Document structure and link checks establish package consistency only. They do not verify application behavior, current source, issue synchronization, deployment or product readiness. The containing Git revision identifies this package edition; deployment evidence must identify the actual built and deployed application revision separately.

## 4. Historical application evidence

The retained application handoff reports successful normal login and SQL access through App Service's system-assigned managed identity, with end-user authorization enforced inside the application. Preserve that reported evidence. A current access limitation does not invalidate a previously valid result; an old result also does not certify a new deployed revision.

Earlier reports discussed lifecycle/PR/check/deployment work, dirty worktrees, unmerged changes, workflow runs labelled `main` and lifecycle/Snapshot overlap. These are historical investigation topics. Reconcile the actual application records before assigning current status or repeating work. The detailed underlying runtime evidence is not reproduced in this planning package and must be obtained from the application workspace when needed.

During the 22 October documentation session, access to the historically identified application repository returned 404. This establishes an access limitation for that review, not missing code, a deleted repository or a regression. A later report that a connection problem was resolved does not by itself verify application behavior or deployment.

The planning record does not establish whether a prior artifact-generation prompt created Plan/Task issues or configured a Project. Inspect current files, issue identities, Project configuration and generation reports before creating work. Unverified execution is not evidence that the task was never run.

## 5. Decisions to preserve

1. **SQL and Databricks are baseline provider scope.** Registry bindings, compatible application authorization, execution contracts and readiness belong across P01/P02/P04/P05/P07. P15 covers further expansion.
2. **Qualification is scoped.** Record provider, environment and workflow evidence independently. An explicitly limited pilot may qualify one route while another remains pending. Common contracts neither prove live connectivity nor authorize cross-provider joins.
3. **Application authorization and workload identity are distinct.** Preserve the App Service SQL system-assigned managed identity direction and required native workload grants. Qualify Databricks identity and connector separately.
4. **Business/data owners approve meaning.** The Registry represents versioned approved definitions at runtime. Recipes define approved analytical methods; question/output templates reference approved identities and versions.
5. **Preserve engineering boundaries.** Retain accepted 2F.1 trace-only behavior and repairs. New enforcement requires an accepted decision. Keep 2F.1a conditional, 2G provisional, and 2F.3 semantics separate from 2F.5 relationship evidence.
6. **One canonical Task has one accountable Plan.** Supporting phases, outputs, requirements and releases are links. Preserve existing canonical IDs and accepted work.
7. **Dependencies identify outputs and consuming activities.** H required outputs, C shared contracts, G acceptance gates and O conditional relationships are distinct. Early P07 contracts and later integrated evidence must not become whole-Plan circular blockers.
8. **Preserve active work and newer candidates.** Inspect staged/unstaged/untracked changes, other worktrees, unmerged branches and any later Master such as `MASTER_PLAN_V2.md` if present. Do not reset, delete or replace them by assumption.
9. **Separate document state, work state and evidence maturity.** Draft/reviewed/adopted, implementation progress and designed/implemented/verified/qualified are different facts. Unknown is not missing, failed or complete.
10. **Saved prompts are task templates.** Reading a prompt does not execute it. Continuation, planning synchronization and implementation are separate scopes governed by the active request.

### Identifier namespaces

| Namespace | Meaning |
|---|---|
| Master Phases 0–7 | Original engineering scope/history. |
| Detailed 2F slices; provisional 2G | Specific engineering and forward-reference slices. |
| Later provider Phase 3 alias | Historical naming difference from Master Phase 4; reconcile actual task anchors. |
| P01–P15 | Delivery Plan aliases, not phase or issue numbers. |
| R1–R4 | Product release outcomes. |
| Executive Phases 1–3 | Presentation grouping: 1 = readiness/R1; 2 = R2/R3; 3 = R4/conditional expansion. |
| Historical D4–D6; September D04–D06 | Distinct source namespaces. |

The crosswalk is many-to-many. P04 includes 2F.3 semantics, 2F.5 relationships and provider scope; 2F.4 contributes to P05 presentation and P09 authoring. Use the [lineage reference](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md) for complete mappings and legacy aliases.

## 6. Evidence still required

The U identifiers below are reconciliation questions, not new implementation Task IDs.

| Ref | Unresolved question | Required evidence |
|---|---|---|
| U01 | Application source and target | Repository/root, active branch/HEAD, worktree state and relevant unmerged PRs. |
| U02 | Operative Master and authority | Current Master/ADRs, later candidates and accepted-change records. |
| U03 | Existing planning synchronization | Existing Plan/Task identities, Project configuration, generated files and sync report. |
| U04 | Login, identity and environment | Current evidence only where a regression or new qualification claim requires it; retain valid prior results. |
| U05 | Workflow/source/artifact lineage | Trigger chain, caller/callee definition refs, checkout SHA, built artifact and deployed revision. |
| U06 | Business/provider pilot scope | Selected question, accountable owners, reference calculation, approved bindings, access cases and qualification status. |
| U07 | Acceptance and external decisions | Scope-specific A01–A10 and broader-gate evidence with accountable decisions. |

A workflow display label such as `main` does not identify all definition, checkout, build or deployment revisions. Inspect those separately; do not dispatch a workflow merely to restore planning context.

## 7. Next bounded activity

Reconcile the application baseline and existing planning artifacts for one representative analytical workflow. Produce a compact evidence packet containing source/worktree state; operative Master/ADR/task revisions; existing issue/PR/Project records; relevant CI/artifact/deployment lineage; selected question/reference/provider scope; and output dispositions of satisfied, partial, missing, unknown or superseded.

Then identify the smallest remaining Task, its accountable Plan/output, prerequisites and acceptance evidence. Clearly labelled synthetic contract/framework work may proceed independently where justified; it cannot substitute for business sign-off or live-provider qualification.

If application evidence is unavailable, finish independent documentation work and request only the connected-session report or exact target information needed. Do not infer an empty application or duplicate existing work.

When planning synchronization is explicitly requested, use the [project setup prompt](AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md). Generate/reconcile all Plan definitions and registers, but detail only justified near-term Tasks. Prepare concrete operations, perform authorized supported changes and verify actual results. Unsupported operations remain explicit pending items.

## 8. Prompt selection

| Activity | Entry point |
|---|---|
| Restore context read-only | [New-session prompt](ASKTD_NEW_SESSION_PROMPT.md). |
| Generate/reconcile planning artifacts and GitHub work | [Project setup prompt](AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md), with the [artifact-generation specification](ASKTD_COPILOT_ARTIFACT_GENERATION_PROMPT.md). |
| Continue bounded framework implementation after baseline reconciliation | [Framework continuation prompt](AskTD_Framework_Development_Continuation_2026-10-22.md). |

The framework implementation template is intentionally separate from the planning prompts. Merely copying or reading this package authorizes none of those execution tasks.
