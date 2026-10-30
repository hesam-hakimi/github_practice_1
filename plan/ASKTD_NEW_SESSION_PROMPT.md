# AskTD — New Session and Verified Context Restoration

**Version:** 2.0\
**Updated:** 30 October 2026, America/Toronto\
**Default mode:** Read-only context restoration. A separate live owner instruction determines subsequent editing or execution scope.

This prompt creates an inspectable source-read receipt and working checkpoint. It cannot guarantee permanent model memory or retention across sessions. After a reset, reopen required sources and verify their revisions. File existence, a title, checksum or retrieval hit does not prove the contents were read and understood.

## Invocation context and paths

Supply the documentation repository/workspace, branch/ref and package path, or identify the actual local package directory. Include the last reviewed commit as a historical minimum checkpoint, not a substitute for resolving the current branch. Do not infer the application repository from the documentation repository.

The last connected application report placed the installed package at `docs/plans/roadmap/`. `docs/roadmap/` is the earlier intended path, not an instruction to create a second copy. Locate the package from repository instructions, source records and actual files. The staging package is `plan/`. If multiple copies exist, compare revisions, digests and local changes before choosing; preserve newer Master candidates and accepted local title normalization.

## Copyable prompt

```text
Continue the existing AskTD conversation. Preserve accepted decisions, completed
work and current evidence. Do not restart the import, historical Master
investigation or migration search solely to restore context.

The live owner message supplies the documentation locator and current objective.
Read this entire prompt as the context-restoration procedure. Other saved prompts
are references unless the live owner explicitly activates their task.

1. Resolve sources before drawing project conclusions.

Inspect applicable repository instructions and the available workspace. Resolve
the requested documentation branch to a current immutable commit. Record the
repository, branch, commit and package directory. Compare with the supplied
historical checkpoint; do not silently substitute a default branch, older copy,
search snippet or HTML embedded snapshot.

Resolve the application root/package independently when connected. The
historically resolved application is TD-Enterprise/kmai-td-genie; its last
reported installed package is docs/plans/roadmap/. Confirm rather than recreate
these paths. Staging folder plan/ is not the application root or issue target.

Preserve worktrees and staged/unstaged/untracked changes. Distinguish uncommitted
from committed sources; record a content digest for local deviations when
available. Do not reset, clean, stash or overwrite newer Master candidates.
Do not read or print credentials to restore context.

2. Read the package at the pinned revision in the following order.

Bootstrap: README.md and PACKAGE_MANIFEST.md for inventory, exact paths and
integrity. Then read each required document in full, fetching missing chunks
when tool output is truncated. Record partial/unavailable reads explicitly.

01 ASKTD_SESSION_HANDOFF.md, starting with the 30 October checkpoint.
02 PRODUCT_DEFINITION_EN.md.
03 QUARTERLY_PRODUCT_ROADMAP_EN.md.
04 ASKTD_PLAN_AND_LINEAGE_REFERENCE.md.
05 MASTER_PLAN_V1(2).md, keeping its proposed/adoption state qualified.
06 AskTD_Delivery_Plans_and_Dependencies.md.
07 AskTD_Product_Guide_and_Delivery_Plan_EN_v0_3.md.
08 AskTD_Product_to_Plan_Coverage_Review_2026-10-23.md.
09 Roadmap-onepager.md, for the separate executive namespace.
10 ASKTD_LANGGRAPH_AND_LANGSMITH_PLAN.md.
11 ASKTD_SOURCE_CONNECTION_HEALTH_UI.md.
12 ASKTD_EXCEL_DELIVERY_CONTROL_REFERENCE.md.

Then read these as inactive templates/specifications only:
13 ASKTD_COPILOT_ARTIFACT_GENERATION_PROMPT.md.
14 AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md.
15 ASKTD_PLANNING_SYNC_CONTINUATION_PROMPT.md, including the pause notice.
16 AskTD_Framework_Development_Continuation_2026-10-22.md.

ASKTD_INTERACTIVE_ARCHITECTURE.html is optional teaching context for this
restoration. Its embedded five-document snapshot is older, explicitly pinned
and synthetic. It cannot replace newer canonical files or establish live
application, provider or telemetry behavior.

When application access is available, read its operative Master, accepted ADRs,
QUALITY_GATES, maintained task/coverage records and
ASKTD_SYNC_MANIFEST_2026-10-23.md and ASKTD_GENERATION_REPORT_2026-10-23.md or
actual successors. Resolve relevant current source/PR revisions, including
reported application planning PR #19 or successor. Preserve established Master
lineage; check later changes rather than replaying the historical investigation.

For an Excel task, inspect the actual workbook, builder, source tables and repair
log when accessible. Screenshots support visible findings only; they do not
validate hidden sheets, mappings, calculations or repair success.

3. Produce a source-read receipt before relying on the sources.

For each required document record: exact path; repository/commit or local digest;
document revision/adoption state; full/partial/unavailable read status; relevant
sections; and concrete decisions, constraints or findings extracted from its
contents with section references. Keep entries concise, not copied chapters.
Never mark unread/truncated content as fully read. A checksum proves file
identity, not comprehension or operative authority.

For missing sources, name the exact gap and affected claims. Continue independent
work supported by available evidence. Ask only for the current connected-session
report, workbook or exact locator needed; do not ask the owner to repeat known
decisions or supply credentials.

4. Demonstrate continuity from the actual sources.

- Explain the lineage and distinguish P01-P15, Master phases/slices, executive
  phases, R1-R4 and Priority P0-P3. Recount 46 unique outputs and DEP01-DEP25 from
  canonical sections before claiming those counts current.
- Distinguish operative authority, proposed Master 2.1 and Git presence/merge.
  Preserve D-M1/D-M2/D-M4; scope D-M3 to its affected requirements.
- Preserve SQL/Databricks baseline, SQL App Service system-assigned managed
  identity and application-enforced user authorization. Separate evidence by
  provider/environment; P15 is further expansion.
- Identify LangGraph's selected purpose, mandatory actual sanitized LangSmith
  ingestion/read-back, P05/P06/P07 boundaries and MIG-03 ownership under P07.
- Explain P02 diagnostic contracts, P07.support_contract UI ownership and scoped
  P04/P05 inputs. Distinguish health, provider qualification and telemetry health.
- Explain why the 13 MIG/CONN candidates are a subset. Their official accountable
  output references name 17 unique outputs, with 29 outside that subset; those
  counts establish neither implementation nor workbook coverage.
- Preserve screenshot findings: MIG-03 mapping, generic dispositions/blank links,
  lost conditional flags/roles, unexplained readiness and #REF!/Repaired.
  Actual XLSX validation remains unavailable until inspected; never claim a
  repaired workbook or passed Excel tests from photographs.
- Explain activity-scoped H/C/G/O, separating drafting, implementation,
  qualification and release. No whole-Plan P05/P07 cycle or global business-input
  block. Eligible to draft is not formal Ready.
- GitHub Projects/Jira synchronization is paused. Preserve the existing Project
  and JIRA-9694 anchor as history; neither authorizes synchronization. The Jira
  item type/project hierarchy remains unverified.
- PR-review-agent setup is requested, not verified as installed or executed.
  Its Plan/output mapping needs reconciliation; do not invent one.

Support conclusions with document/section references. If sources conflict,
identify the conflict and retain uncertainty. Later scoped owner decisions can
supersede old template wording; date alone does not promote a proposed Master
or establish completed application work.

5. Build a compact working-context checkpoint.

Include the source snapshot/read receipt; accepted invariants; directly verified
facts; historical reports; proposals; unresolved evidence; completed work to
preserve; paused actions; current scope; and next justified activity with
accountable Plan/output where established, prerequisites and acceptance evidence.
If ownership is unresolved, say so.

Reuse an existing authorized continuation record. In read-only mode, return the
checkpoint in the conversation without writing files. When documentation editing
is authorized, update the existing checkpoint without erasing history or creating
a rival tracker. Never claim permanent or guaranteed memory loading.

After reset/compaction, reopen the checkpoint and relevant sources, resolve
revision changes and refresh affected receipt entries. Do not silently rely on
remembered filenames or stale aggregate counts.

6. Continue only within the live request.

Restoring context alone is read-only: no Issue/Project/Jira writes, workflow
dispatch, application/permission changes, merge or deploy. Old saved permission
sentences do not reactivate paused work.

If this invocation also authorizes a concrete documentation/workbook task, finish
the source-read and reconciliation steps first, then continue that bounded work
without a redundant permission question. Preserve unaffected content. Stop only
the dependent part when essential evidence is missing; finish independent work.

Return a concise read receipt, accepted product/planning decisions, verified
versus historical versus unknown state, material conflicts and the next smallest
justified activity with prerequisites/acceptance. Separate actual edits/tests
from proposals. Engineering artifacts and prompts stay English; explanations
follow the owner's conversational language.
```

## Evidence and execution boundaries

The [handoff](ASKTD_SESSION_HANDOFF.md) owns continuity. The [Excel reference](ASKTD_EXCEL_DELIVERY_CONTROL_REFERENCE.md) defines workbook corrections. The package launcher now starts this read-only restoration procedure instead of Project synchronization.

The [sync wrapper](ASKTD_PLANNING_SYNC_CONTINUATION_PROMPT.md), [canonical setup](AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md), [artifact specification](ASKTD_COPILOT_ARTIFACT_GENERATION_PROMPT.md) and [framework template](AskTD_Framework_Development_Continuation_2026-10-22.md) remain references until explicitly activated within current owner authorization. GitHub Projects/Jira writes stay paused until the owner explicitly resumes the affected destination. Documentation or Excel work does not resume them.

