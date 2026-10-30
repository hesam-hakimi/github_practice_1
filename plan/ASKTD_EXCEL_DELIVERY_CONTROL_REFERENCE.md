# AskTD — Excel Delivery Control and Coverage Reconciliation

**Document ID:** ASKTD-EXCEL-DELIVERY-CONTROL\
**Version:** 1.0\
**Prepared:** 30 October 2026, America/Toronto\
**Status:** Workbook requirements and screenshot-based findings. No workbook repair, formula validation or current application acceptance is established here.

## 1. Purpose and authority

The owner requested an English Excel version of delivery planning, dependency management, team allocation and project visibility. GitHub Projects and Jira synchronization are paused because access was incomplete. Excel is a temporary operational view; repository requirements, architecture decisions and acceptance records retain their authority.

Preserve the [canonical lineage](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md): Master requirement/revision → engineering phase/slice → delivery Plan → named output → canonical Task/PR → acceptance evidence → release. This document changes planning representation and verification requirements, not product scope or operative Master authority.

The baseline is P01–P15, 46 outputs, DEP01–DEP25, A01–A10 and D01–D18. Resolve later accepted changes before treating these counts as current. Master phases/slices, delivery Plans, releases R1–R4, executive phases and Priority P0–P3 are separate namespaces.

The [migration](ASKTD_LANGGRAPH_AND_LANGSMITH_PLAN.md) and [connection-health](ASKTD_SOURCE_CONNECTION_HEALTH_UI.md) amendments define 13 local MIG/CONN candidates. They are a subset of the product backlog, not 13 verified remote issues or a full decomposition of all outputs.

## 2. Evidence available on 30 October

The owner supplied ten photographs showing Tasks, Plans and Outputs in `AskTD_Delivery_Control.xlsx`. Excel displays `Repaired` in the title and visible `#REF!` errors in Plan counts. The actual XLSX, repair log, builder and contents of the other sheets were not supplied for this review.

The documentation branch was resolved before comparison. Its pre-update head was `dadff5d91a97f6473b0064eebf57b131e2d0d90d`; the lineage and amendment files supplied the comparison definitions. This is not the workbook generation revision or an application/deployment revision.

| Evidence | Supports | Does not establish |
|---|---|---|
| Supplied workbook photographs | Visible rows, labels, values and errors | Hidden/filtered rows, complete mappings, formula behavior, integrity or native recalculation |
| Current planning documents | Intended ownership, scope, dependencies and task requirements | Current implementation, assignments or acceptance |
| Earlier connected-session reports | Historical application reconciliation/publication observations | Current source, PR, Project or Jira state |
| Missing XLSX or inaccessible source | An exact evidence gap | Missing code or failure in other sessions |

## 3. Recorded workbook findings

These are review-finding identifiers, not Task IDs or new outputs. Recheck them against the current workbook before editing.

| Finding | Observation and consequence | Correction or verification |
|---|---|---|
| XL-01 | Visible Tasks contains MIG-01–MIG-08 and CONN-01–CONN-05 only; a full product backlog is not demonstrated. | Reconcile all outputs with existing work and bounded remaining-work or decision records. Retain these candidates as a subset. |
| XL-02 | MIG-03 is shown under P05; migration §6 assigns it to P07. | Restore P07 ownership and P07.event_contract, P07.metering and P07.support_contract references unless a later accepted change supersedes them. |
| XL-03 | Outputs use `Proposed baseline` as Primary_Disposition; evidence/task references are blank and remaining-work text is generic. | Separate adoption/proposal state from implementation disposition; restore specific evidence, work and keyed mappings. |
| XL-04 | Visible conditional/scoped flags are all `No`, although P03 selected enforcement, P11 reuse and P15 expansion have conditions. | Preserve applicability, conditional and scoped-decision flags independently of primary disposition. |
| XL-05 | Candidate roles are unassigned because no roster exists; the amendment documents already specify roles. | Populate supported roles; leave personal identities unset until approved. |
| XL-06 | Several rows say `Not ready`/`Resolve prerequisites` while the blocker says `none`. | Identify the affected activity, unmet input/owner/decision, responsible role and next action. |
| XL-07 | Plans.Task_Count and Plans.Output_Count show `#REF!`; title says `Repaired`. | Preserve source/repair log, diagnose references/tables/names and verify the exported workbook. Do not hide errors with zero or hardcode totals. |

### 3.1 Candidate ownership

| Accountable Plan | Visible candidate count | Expected from amendment definitions |
|---|---:|---:|
| P02 | 2 | 2 |
| P05 | 6 | 5 |
| P06 | 1 | 1 |
| P07 | 4 | 5 |
| P01, P03, P04 and P08–P15 | 0 | 0 in this subset |
| Total | 13 | 13 |

MIG-03 is the observed owner mismatch. Supporting references do not create a second accountable Plan. Current canonical Tasks may legitimately consolidate or split candidates; preserve accepted identity/scope rather than force candidate counts onto the application.

### 3.2 Direct output references are not acceptance coverage

Unique output identifiers in the accountable-output columns of migration §6 and connection-health §6.1 give:

| Plan | Canonical outputs | Direct candidate references | Outside this subset |
|---|---:|---:|---:|
| P01 | 4 | 0 | 4 |
| P02 | 4 | 4 | 0 |
| P03 | 3 | 0 | 3 |
| P04 | 4 | 0 | 4 |
| P05 | 5 | 5 | 0 |
| P06 | 3 | 3 | 0 |
| P07 | 6 | 5 | 1 |
| P08 | 3 | 0 | 3 |
| P09 | 2 | 0 | 2 |
| P10 | 2 | 0 | 2 |
| P11 | 2 | 0 | 2 |
| P12 | 2 | 0 | 2 |
| P13 | 2 | 0 | 2 |
| P14 | 2 | 0 | 2 |
| P15 | 2 | 0 | 2 |
| Total | 46 | 17 | 29 |

The unreferenced P07 output is P07.feedback. P04.bindings is an input/coordination obligation, not proof that a candidate produces the full output. Candidates can cover only part of an output: diagnostics alone do not meet all P02 authorization/route acceptance. Thus 17/46 is not a completion percentage or a verified workbook mapping count. Read Task_Output_Map, Task_Details, Dependencies and Acceptance before certifying coverage.

## 4. Whole-program coverage contract

Every current output has exactly one primary implementation disposition: satisfied, partial, missing or unknown, qualified by scope, revision and observation date. Preserve superseded history separately if an accepted successor changes the register. `Proposed baseline` belongs in an adoption/proposal field.

Every output must be explicitly accounted for through one or more of:

1. Existing canonical work and acceptance evidence for its scope.
2. Bounded remaining-work records linked through stable Task/output keys.
3. An explicit decision, conditional/deferred scope or evidence gap with responsible role, next action and review/activation condition.

A decision/evidence gap makes an output accounted for, not implemented or delivery-covered. Report accounting, remaining-work coverage, Ready work and accepted scope separately. Completed outputs need no fabricated Tasks. Later work can remain at outcome/contract/decision depth. Do not force exactly one Task per output or one vague catch-all Task per Plan.

For partial/missing near-term outputs, define actual remaining work instead of repeating `Reconcile against the Master`. Match existing Tasks/PRs before allocating provisional local IDs. External IDs require verified remote records. The two earlier full payloads are a subset of the 13 MIG/CONN identities, not two additional tasks.

The connected-agent report corrected historical primary counts to 3 satisfied, 20 partial, 22 missing and 1 unknown, with conditional/scoped flags separate. Preserve that dated comparison, not a required current distribution. Reconcile by output ID; do not restore obsolete totals or erase history with generic unknown values without explaining the evidence change.

### 4.1 Task detail and existing work

Use lineage §10.1: one Plan; exact outputs; qualified Master/requirement and engineering anchors; bounded scope/exclusions; existing-work disposition; typed inputs; owner/reviewer/decision roles; provider/environment; testable acceptance and evidence location; release contribution; work state/maturity; unresolved questions.

Reconcile historically reported P03 lifecycle completion and SQL diagnostics instead of rebuilding them because a spreadsheet lacks links. SQL and Databricks remain baseline across P01/P02/P04/P05/P07. SQL evidence does not qualify Databricks or move it into optional P15 expansion.

PR-review-agent setup is requested engineering enablement. A prompt was delivered in the conversation; installation, active agents and posted reviews were not verified. Inspect existing instruction/agent files before defining remaining work. Its Plan/output mapping remains unresolved until reconciled; do not invent a new Plan or forty-seventh output. Record a scoped mapping decision if needed.

## 5. Dependencies and readiness

Keep the 25 portfolio relationships distinct from task/activity instances. Each relationship retains producer, exact output/input, consumer, blocked activity, type, applicability, satisfaction evidence, responsible role and next action.

- H blocks only its named activity while the applicable output is unmet.
- C means contract coordination, not reciprocal whole-Plan blocking.
- G blocks affected acceptance/activation, not all preparation.
- O has an explicit condition and H/C/G effect; unknown applicability is not satisfied or automatically inactive.

Distinguish definition/drafting, implementation, qualification and release gates. An implementation prerequisite does not automatically block task definition, contract drafting or labelled fixture tests. Early P07 contracts and later qualification must not create an artificial P05/P07 cycle.

Reuse actual Ready/Done criteria and QUALITY_GATES. No approved roster may prevent formal Ready, but does not erase known roles or prevent backlog definition. Keep artifact state, work state, readiness, blocking and evidence maturity separate. Done, merge and closure do not prove product/provider acceptance. Require qualified only when scoped acceptance calls for it; documentation/synthetic tasks may finish at verified.

D-M3 applies only to Power BI integration, interactive chart actions and dashboard coverage, not all MIG/CONN work. Missing Deposits input blocks affected business/reference acceptance; justified synthetic framework work may proceed with that limitation recorded.

## 6. Workbook requirements

Maintain one owning location per editable fact. Preserve human edits, IDs, notes, assignments and dates by stable key during sorting/import/refresh. No implicit repository or tracker writeback.

| Area | Required behavior |
|---|---|
| Dashboard | Calculated Plan/release/owner coverage, unassigned/blocked work, reviews, decisions and acceptance gaps; source as-of context and navigation. Unique counts; Task completion never implies release acceptance. |
| Plans / Outputs | All Plans/outputs, scoped disposition, separate conditional/decision flags, evidence/remaining-work links and calculated counts. |
| Tasks / Task_Details | Usable daily view with Plan, role, approved people if known, work state, activity, readiness, exact blocker/action and release scope; accessible detailed lineage and acceptance. |
| Task_Output_Map | Normalized many-to-many stable keys; no substring or comma-string coverage calculations. |
| Dependencies | Typed output/activity relationships, conditions and evidence; distinguish source portfolio rows from instances. |
| Acceptance / Releases | Scope-specific evidence/gates; SQL, Databricks and LangSmith qualify separately by environment. An evidence register is not live telemetry. |
| Decisions / Team | Bounded decisions, accountable roles, next actions and approved roster mappings; unapproved identities/dates stay blank. |
| Reference / Checks | Source path/revision/date/read limits, vocabulary and refresh rules; independent checks. No operational formula depends on a global Checks PASS cell. |

Small support tables may share a sheet. Do not duplicate Tasks into 15 Plan sheets. Preserve the current structure when a focused repair suffices.

Use a real macro-free XLSX with tables, filters, freeze panes, readable widths/wrapping, useful dropdowns and distinct editable/imported/calculated cells. Dates are numeric when supplied. Invent no estimates, capacity, sprints or deadlines. Distinguish blank, zero, unknown and not applicable.

Keep formulas transparent and resilient to supported sorting/new rows. Fix bad references instead of masking errors or replacing calculations with static totals. The workbook must be usable without live Jira/GitHub Projects access. Use English and repository-relative provenance, with no personal repository URLs.

On refresh, separate source changes from operational edits, expose conflicts and preserve later accepted/local changes. Explain which results update automatically and which require rebuilding/revalidation.

## 7. Verification of a corrected workbook

When editing is requested, inspect the XLSX, available repair log, builder and source tables and preserve the original. Photographs do not establish repair. If the file is unavailable, finish independent reconciliation and request only the file or exact current connected-session report needed.

Verify:

1. Unique Plan/output/Task keys, valid foreign keys, all current outputs accounted for, conditional flags and MIG-03 ownership.
2. Row-level evidence and remaining-work/decision references; no duplicate Tasks, erased accepted work or invented implementation.
3. Typed dependencies and activity-level hard-cycle checks. Generation-only checks must show their revision and need for revalidation after edits.
4. Actual references/tables/names, recalculation, filters/dropdowns and row extension. Inspect the saved/reopened file and whether Excel repairs it. State the engine actually tested; another engine is not native Excel proof.
5. Disposable-copy tests: missing owner, duplicate/missing keys, sorting/new row, one prerequisite met while another remains open, conditional relationships, Done without evidence, blank versus zero; verify summaries and next actions react.
6. Error scan and visual review of affected sheets; totals reconcile to underlying rows. A screenshot, cached PASS or successful export is insufficient.

Deliver the corrected workbook and concise provenance, validation and update instructions only when editing is requested. Do not resume tracker writes, modify application code/permissions, merge or deploy as part of workbook work. Commit/publish the workbook only within a corresponding owner instruction.

## 8. Next smallest justified activity

Reconcile actual workbook output-to-task coverage and repair calculations using current application reports where accessible. This maintains the planning representation and creates no new delivery Plan; underlying product gaps retain their own Plans/outputs. The immediate known mapping correction is MIG-03 under P07.event_contract/P07.metering/P07.support_contract.

Prerequisites: actual workbook or generated tables, relevant maintained application reports and pinned documentation. Missing application access does not prevent documenting screenshot findings and proposed mappings, but limits implementation claims.

Acceptance: all outputs have explicit dispositions and evidence/work/decision mappings; no duplicates; conditions and roles preserved; unresolved evidence visible; calculations pass scoped checks with engine limits stated. Ready-to-assign additionally requires actual Ready criteria and an approved roster.

## 9. References

- [Session handoff](ASKTD_SESSION_HANDOFF.md) and [new-session prompt](ASKTD_NEW_SESSION_PROMPT.md).
- [Product](PRODUCT_DEFINITION_EN.md) and [quarterly roadmap](QUARTERLY_PRODUCT_ROADMAP_EN.md).
- [Delivery portfolio](AskTD_Delivery_Plans_and_Dependencies.md) and [lineage](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md), especially §§6, 7.1 and 10.1.
- [Migration](ASKTD_LANGGRAPH_AND_LANGSMITH_PLAN.md) §6 and [connection health](ASKTD_SOURCE_CONNECTION_HEALTH_UI.md) §6.1.
- [Manifest](PACKAGE_MANIFEST.md): integrity is not implementation or authority evidence.
