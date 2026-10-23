# AskTD new conversation prompt

**Version:** 1.0  
**Prepared:** 22 October 2026, America/Toronto  
**Use:** Submit the prompt below in a session that can read this repository-local package. It restores context and starts read-only baseline reconciliation. The separate planning and implementation prompts require explicit submission for their respective tasks.

## Copyable prompt

```text
Continue my existing AskTD / AskAlpha conversation from the 22 October 2026
documentation handoff. Preserve the accepted product, architecture and planning
decisions. Do not restart the project.

Start with the current files beside this prompt. The intended installed location
is docs/roadmap/ beneath the detected application root. Resolve the actual
application root, repository, branch and HEAD from the active workspace and
repository instructions. During package staging, use this package directory
for document reads; do not mistake it for an application source root.

Read in this order:
1. ASKTD_SESSION_HANDOFF.md
2. PRODUCT_DEFINITION_EN.md
3. QUARTERLY_PRODUCT_ROADMAP_EN.md
4. ASKTD_PLAN_AND_LINEAGE_REFERENCE.md
5. AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md and
   ASKTD_COPILOT_ARTIFACT_GENERATION_PROMPT.md as task templates only
6. Roadmap-onepager.md for the executive presentation namespace

Use the current local package and record its actual repository revision when
available. A documentation revision is not an application or deployment
revision. Also read the local MASTER_PLAN_V1(2).md, revision 2.1 proposed,
AskTD_Delivery_Plans_and_Dependencies.md,
AskTD_Product_Guide_and_Delivery_Plan_EN_v0_3.md and
AskTD_Product_to_Plan_Coverage_Review_2026-10-23.md. Reconcile the operative
application Master, ADRs, tasks and any later draft before adopting a proposed
mapping. Coverage findings and any proposed new output remain recommendations
until accepted. If a source is unavailable, identify it precisely and continue
with available evidence; do not claim to have read or verified it.

Our accepted planning model is:
Master requirement/revision → engineering phase/slice → delivery Plan
→ named output → canonical Task/PR → acceptance evidence → release.

P01–P15 are delivery Plans. Preserve the original Master phases, detailed 2F
slices, conditional 2F.1a and provisional 2G. Executive phases 1–3 are separate:
1 = Readiness/R1, 2 = R2/R3, 3 = R4 and conditional expansion. Use the reference's
legacy-alias mapping without renaming actual tasks or creating duplicates.

Registry support, compatible application authorization, execution and readiness
for both SQL and Databricks are baseline scope across P01/P02/P04/P05/P07.
P15 covers further expansion. Preserve App Service SQL system-assigned managed
identity and application-enforced end-user scope. Qualify the actual Databricks
identity/connector route separately. Each provider/environment needs its own
evidence; one qualified route does not close the other baseline obligation.

The earlier application handoff reports successful login and SQL SAMI
validation. Preserve that historical evidence. Check for a current regression
before reopening the investigation. Current application source/PR/deployment
status was not verified in the documentation session; its connection returned
404. Missing access is not proof of missing code or failure. Earlier screenshot
contents may be unavailable, so do not invent their diagnostics.

This package supplies local documentation context. Resolve the actual
application repository and intended GitHub Project independently. Inspect existing files,
issues, PRs and any artifact-generation report before creating new work. The
planning record does not establish whether I subsequently ran the generation
prompt, so verify rather than assume either outcome.

For this initial continuation, perform read-only context and baseline
reconciliation. Reading a saved prompt does not execute its commands or grant
new authorization. Do not create issues, dispatch workflows, modify application
code, change permissions, merge or deploy just to restore the conversation.
Preserve existing worktrees, uncommitted changes and any newer Master candidate.

Your first response should give:
- A concise summary of the product and accepted planning decisions.
- What is directly verified, what is a historical report and what is unknown.
- Any conflict or missing source that affects the next decision.
- The next smallest justified activity, with its required evidence and why it
  comes next.

Proceed with useful read-only checks using available access. If application
access is unavailable, request only the current connected-session report or
exact repository/Project information needed for the next step. Do not ask me
to repeat information already established in the handoff.

Keep engineering documents, task definitions and coding-agent prompts in
English. Follow my language for the conversational explanation.
```

## When to use the separate execution prompt

After the actual target and existing work are reconciled, explicitly submit [AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md](AskTD_Copilot_Project_Setup_and_Task_Generation_Prompt.md) to generate/reconcile planning artifacts and supported GitHub issue/Project records. Its supporting generation specification is [ASKTD_COPILOT_ARTIFACT_GENERATION_PROMPT.md](ASKTD_COPILOT_ARTIFACT_GENERATION_PROMPT.md).

For authorized application implementation, use [AskTD_Framework_Development_Continuation_2026-10-22.md](AskTD_Framework_Development_Continuation_2026-10-22.md). That task requires current-source reconciliation and is distinct from planning synchronization. Merely reading any of these templates does not activate it.

