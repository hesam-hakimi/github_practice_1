# AskTD / AskAlpha — Product-to-Plan Coverage Review

Review date: 23 October 2026 (UTC)  
Documentation baseline: 22 October 2026 continuity update  
Status: read-only documentation assessment; recommended refinements are not adopted changes

## 1. Conclusion

The combined maintained Master, delivery portfolio and lineage reference cover the major capabilities in the Product Definition. No whole top-level product capability was found without a plausible owning delivery Plan.

The plan is not yet precise enough to generate a complete, dependable developer backlog from the short Plan summaries alone. Several requirements already stated in the Product Definition and Master need explicit output ownership, producer/consumer dependencies or testable acceptance clauses. The strongest findings concern:

1. Organization/user capability administration under P10.
2. Administrator-visible operational, quality and usage information under P07.
3. Schedule frequency and conditional cost preview under P12, with selected P07/P10 inputs.
4. Owner improvement analytics and published-template usage traceability across P07/P09/P13.
5. Detailed user journeys and controls under P05/P06/P08/P09/P12 that are present in the Master but abbreviated in the lineage reference.

These are documentation and decomposition findings. They do not establish missing code, a failed deployment, or completed implementation. The operative application Master, ADRs, existing tasks/PRs and current deployment were not available for this review. Master revision 2.1 remains a proposed maintained working copy until reconciled with that evidence.

## 2. Sources and version basis

The DCM branch `xdoc` was resolved during this review to commit `fe5ba775bd5a7d9bf0ef0fbf3ea333eabb094b4e`. No later branch revision was returned by that check. This is a point-in-time observation, not a claim that the branch cannot subsequently change.

| Ref | Source inspected | Version / role |
|---|---|---|
| S1 | `AskAlpha_Product_Definition_FA_2026-10-13.docx` | Persian Product Definition, internal v1.0 proposed, 13 October. All five pages read. |
| S2 | [PRODUCT_DEFINITION_EN.md](https://github.com/hesam-hakimi/dcm/blob/fe5ba775bd5a7d9bf0ef0fbf3ea333eabb094b4e/docs/askalpha/PRODUCT_DEFINITION_EN.md) | English v1.2 proposed, 22 October. More detailed product baseline used for clause coverage. |
| S3 | `MASTER_PLAN_V1(2).md` | Maintained working copy, revision 2.1 proposed, 22 October. Not assumed to have replaced the operative application Master. |
| S4 | [ASKTD_PLAN_AND_LINEAGE_REFERENCE.md](https://github.com/hesam-hakimi/dcm/blob/fe5ba775bd5a7d9bf0ef0fbf3ea333eabb094b4e/docs/askalpha/ASKTD_PLAN_AND_LINEAGE_REFERENCE.md) | v0.4, 22 October. Delivery Plan/output ownership, crosswalk and dependency register. |
| S5 | `AskTD_Delivery_Plans_and_Dependencies.md` | Delivery portfolio v0.2, 22 October. Fuller Plan outcomes, acceptance and sequencing. |

The Product Definition located in the supplied files is the older Persian document. A separate current English Product Definition file was not located there during this search; S2 was read directly from DCM. The older Persian document and newer English document must not be treated as equivalent translations of one revision. In particular, task generation from S1 alone would omit detail now present in S2 about preferences, scheduling, administration and operating costs.

Source handles for reproducibility:

- S1: `libfile_5862b6833a2481918ac7e2fd4f49c0a9`, file version 1.
- S3: `libfile_f3a37a7311108191af8469304d253bcf`, file version 1.
- S4 maintained file: `libfile_f2101f552b0081919b676896f250c2ca`, file version 1.
- S5: `libfile_e5e7990837308191b4d07be96d59572e`, file version 1.

File-storage version numbers are distinct from the internal document revision numbers above. This review does not supersede a newer Master candidate or infer that one is absent from an inaccessible workspace.

## 3. How coverage is classified

- **Covered:** the combined documents contain the requirement and a recognizable Plan/output responsibility. This says nothing about implementation completion.
- **Refine:** product scope exists, but explicit output acceptance, ownership or a dependency needs to be carried into the executable plan.
- **Conditional:** the behavior applies only when its feature or approved policy is selected; it must not become an unconditional blocker for unrelated work.
- **Decision pending:** an accountable business, security, operational or product owner must supply a value or decision. An empty value is not automatically missing software scope.

The C01–C35 and REC01–REC05 identifiers below are local audit references, not canonical Task IDs, release labels, issue numbers or new Master requirement IDs. Grouped checks are deliberately not used to calculate a percentage: the result would depend on arbitrary clause grouping.

## 4. Product-to-output coverage matrix

| Audit ref | Product requirement and source | Existing delivery ownership | Assessment and acceptance to retain or clarify |
|---|---|---|---|
| C01 | Deposits-first, approved natural-language analysis without requiring SQL/table knowledge; S2 §§1, 3; S1 core journey | `P01.scope`, `P01.reference_cases`; `P05.analysis_contract`, `P05.curated_templates`, `P05.correctness_evidence` | **Refine acceptance.** Scope is covered. Demonstrate own-wording and approved-template entry through the rendered user journey, with focused clarification and approved reference answers. Business examples remain illustrative until approved. |
| C02 | Visible metric, source, as-of date, period, filters and limitations; comparisons/trends and safe unsupported outcomes; S2 §3 | `P04.semantic_bundle`; `P05.result_contract`, `P05.curated_templates`, `P05.correctness_evidence` | **Covered; retain user-visible checks.** Contract fields must reach the answer presented to the user. Include ambiguous/unsupported/insufficient-data outcomes and approved comparison behavior. |
| C03 | Deterministic presentation where eligible; AI formatting separately approved; formatting preserves values and meaning; S2 §3, S3 §8.3 | `P05.curated_templates`, `P05.correctness_evidence`; downstream P06/P14 consumers | **Refine acceptance.** Test deterministic eligibility, approved AI fallback when applicable, and a safe outcome when neither route is eligible. If both routes are enabled, compare them to the same validated result. |
| C04 | No invented joins, unsupported causality or analytical meaning; S2 §§3, 9; S3 §3.2 | `P04.relationship_evidence`; `P05.analysis_contract`, `P05.correctness_evidence`; `P06.context_evidence` | **Refine acceptance.** Join boundaries are explicit. Add a negative case proving simultaneous changes do not become an unsupported causal explanation. Carry the same constraint into reports. |
| C05 | Distinct business-user, manager, content-owner, metric-owner and administrator responsibilities; S2 §2 | P01/P02/P04/P05/P07/P08/P09/P10/P12/P13/P14, according to function | **Covered overall.** Product/operations administrators have the weakest deliverable detail; see C23–C27. Named people and actual approval authority remain decisions, not inferred assignments. |
| C06 | Owner creates reusable questions without application-code changes for already approved analysis; parameters/defaults/audience/layout/context; S2 §4, S3 §3.4 | `P09.authoring`; selected P04/P05 contracts and approved templates | **Refine acceptance.** Demonstrate no-code creation and preview by an authorized owner. Preserve approved IDs/versions and permitted parameters. Do not promote illustrative defaults into business rules. |
| C07 | Reference preview, independent review, versioned publication, revision, retirement and rollback/disable; S2 §4 | `P09.authoring`, `P09.publication`; `P04.publication_contract` | **Covered.** Master and portfolio preserve the workflow. Carry it into task acceptance; do not describe it as newly discovered scope. Curated publication need not wait for the full authoring UI. |
| C08 | Monitor use of published content by stable version; S2 §4 | `P09.publication`; `P07.event_contract`, relevant `P07.metering` | **Refine traceability.** Make the permitted publication-ID/version-to-usage correlation explicit, including its producer output and owner-visible use. |
| C09 | Registry, analytical recipe, reusable question/output template and personal saved question are distinct; S2 §4 | P04/P05/P08/P09 contracts | **Covered.** Preserve separate identities and lifecycles. Authoring a template cannot silently modify the governed analytical definition. |
| C10 | Application-owned conversational state, clarification, intended-only changes, topic resets and session isolation; S2 §5 | `P06.context_contract`, `P06.followup_behavior`, `P06.context_evidence` | **Covered.** Retain current-access checks before context loading/model use and tests that unrelated dates, filters, units and references remain stable. |
| C11 | Long-conversation summaries retain dates, filters, units, warnings and references; S2 §5 | `P06.context_contract`, `P06.context_evidence` | **Conditional and covered.** Test fidelity if compaction is enabled. Do not turn optional summary behavior into mandatory initial-release scope. |
| C12 | Saved analysis/history distinguishes historical answer from an explicit rerun using current data; S2 §5 | `P08.saved_analysis`, `P08.history`; P02 and versioned P04/P05 contracts | **Refine acceptance.** Reopen shows original as-of context without rerunning the analytical query or invoking a model. Explicit rerun reauthorizes and creates a distinct result with its current as-of context. Revoked access must be checked before protected display or reuse. |
| C13 | Explicit preference consent; inspect/edit/remove/disable personalization; request precedence; no raw records/balances in preferences; S2 §5 | `P08.preferences`; P02 scope | **Refine acceptance.** Master already contains the controls. Test disabled personalization, explicit-request precedence, scope validation of defaults and no permanent preference inferred from a single question. Security and approved semantics override both requests and preferences. |
| C14 | Deletion prevents conversational reuse while separately justified audit follows policy; S2 §5 | `P08.history`, `P08.preferences`; applicable P07 retention/audit contracts | **Covered; decision pending.** Portfolio and Master preserve the distinction. Retention periods and authority must be supplied, not invented. |
| C15 | Authorized relevant suggestions, understandable basis, no execution on display, optional preference ranking; S2 §6 | `P13.authorized_suggestions`; selected P02/P04/P06 inputs and conditional P08 preferences | **Covered.** Include basis and no-unrequested-query checks in tasks. Preference-driven ranking remains conditional; basic contextual suggestions need not wait for it. |
| C16 | Owner insights from frequent questions, unsuccessful searches, repeated clarifications and feedback; S2 §6 | `P13.improvement_proposals`; `P07.event_contract`, relevant `P07.metering`, `P07.feedback` | **Refine dependency.** DEP20 explicitly identifies feedback but should identify the permitted usage/outcome/clarification inputs required for the selected aggregates. Protect other users' content and authorization boundaries. |
| C17 | Improvements pass review, testing and release; no autonomous rewriting/retraining; S2 §6 | `P13.improvement_proposals`; `P04.publication_contract` or `P09.publication` | **Covered.** Preserve DEP22 and the controlled publication route. An improvement proposal is not authority to change production semantics. |
| C18 | Complete schedule definition; preview/create/pause/change/cancel; S2 §7 | `P12.schedule_contract` | **Refine acceptance.** Master specifies versions, parameters, reporting-period rule, timezone, recipients, channel and freshness. Test preview and editing explicitly, with revalidation when scope/content changes. |
| C19 | Run history: intended time, actual completion, data as-of, delivery status and safe failure reference; S2 §7 | `P12.run_delivery_evidence`; P07 event/support contracts | **Refine acceptance.** Require the named fields. Separate execution outcome from report/notification delivery outcome. |
| C20 | Owner/recipient/viewer access; secure-link baseline; freshness/failure policy; duplicate prevention; incompatible-version pause/review; S2 §7 | `P12.schedule_contract`, `P12.run_delivery_evidence`; selected P02/P04/P05/P07/P10 inputs | **Covered.** Preserve DST, missed-run, retry and owner-departure cases. Test duplicate report creation and duplicate notifications separately. Attachments remain conditional. |
| C21 | Frequency and, where evidence permits, estimated cost before saving a recurring report; S2 §8, S3 §8.5 | `P12.schedule_contract`; selected P07/P10 inputs | **Refine acceptance and dependency.** Frequency preview is explicit product scope. Estimate availability depends on evidence. Show unknown/unavailable when unsupported; never substitute zero or require every P10 feature. |
| C22 | Health, source/model errors, response time, quality/reference checks, feedback and support correlation; S2 §8 | `P07.event_contract`, `P07.support_contract`, `P07.feedback`; `P05.correctness_evidence` | **Covered foundations; refine visible acceptance.** An authorized administrator must be able to inspect the selected information through an approved view/report. An existing enterprise monitoring surface may suffice. |
| C23 | Active users, popular templates, conversation activity and scheduled-run/delivery observations; S2 §8 | P07 event/metering/support outputs, with each activated feature's evidence | **Refine acceptance.** Define permitted aggregates, counting rules, feature-specific fields and authorized access. Scheduled-report views apply when scheduling exists, not as a blocker for initial operational visibility. |
| C24 | Organization-level users and enabled capabilities, distinct from business-data rights; S2 §§2, 8; S3 §3.1 | P10 broad outcome; P02 authorization and P07 audit inputs | **Explicit deliverable gap.** P10 currently names showback and allowance-policy outputs, without explicit user/capability administration acceptance. Define a bounded administration output/task group. It must not grant business-data access or imply enterprise-directory administration. |
| C25 | Configure/observe spending alerts and allowances; enforce defined behavior at limits; S2 §8 | `P10.allowance_policy`; selected P07/P02 inputs; P12 for applicable scheduled runs | **Refine executable acceptance.** A policy description alone does not prove configuration, alerting or enforcement. Test the approved behavior without weakening correctness, access or provider restrictions. Thresholds remain owner decisions. |
| C26 | All relevant model/query/storage/monitoring/shared costs; failed/retried work; estimates vs reconciliation; S2 §8 | `P07.metering`, `P10.showback` | **Covered.** Preserve actual observations, provenance and shared/idle allocation. Do not assume every question makes every potential model call, or invent prices/savings. |
| C27 | Separate interactive, scheduled and background costs; reproducible assumptions; S2 §8, S3 §8.5 | `P07.metering`, `P10.showback` | **Refine view acceptance.** Show the activity categories and traceable allocation/price assumptions. Missing workload evidence or prices are unresolved inputs. |
| C28 | SQL and Databricks baseline Registry, permissions, execution and readiness; S2 §9 | `P01.provider_coverage`; P02 provider routes; P04 bindings; P05 adapter behavior; `P07.provider_readiness` | **Covered strongly.** Preserve SQL App Service system-assigned managed identity and application-enforced end-user authorization. Qualify Databricks identity/connector separately, per provider and environment. P15 is further expansion. |
| C29 | Current authorization across answers, history, context, suggestions, schedules, reuse and exports; approved model payloads; S2 §§5–9 | P02, relevant feature outputs, P07 scoped acceptance | **Covered.** Source access is distinct from permission to send data to a model. Historical successful login/SQL validation remains evidence; current regressions require current evidence. |
| C30 | Bounded provider-neutral reuse; no blanket replication assumption; S2 §9 | `P11.reuse_policy`, `P11.reuse_evidence`; P02/P04/P05 inputs | **Conditional and covered.** Qualify selected reuse with scope, freshness, version and invalidation evidence. Source size is not an instruction to copy an entire dataset. |
| C31 | Management reports and controlled exports; additional richer interactions; S1 later capabilities; S2 report/output boundaries | `P14.report_contract`, `P14.export_evidence`; P05 validated-result contract and P02 access | **Covered at outcome level.** Management reports and permitted Excel/PDF outputs are proposed release R4 scope. Richer interactions and additional formats remain conditional. Preserve analytical/presentation fidelity and explicitly qualify distribution, size and privacy treatment. |
| C32 | Further provider/source/analysis expansion beyond the SQL/Databricks baseline; S1 later capabilities; S2 §9 | `P15.expansion_decision`, `P15.qualified_extension` | **Conditional and covered.** Each selected extension has its own prerequisites, scope, authorization and qualification under scoped DEP25. Do not imply that all baseline qualification must finish before any expansion planning. Baseline SQL/Databricks support must not be displaced into P15. |
| C33 | Business correctness, trust/privacy, intended-environment reliability and support; pilot vs broader acceptance; S1 release gates; S2 §9 | `P01.reference_cases`, `P01.acceptance_owners`; `P05.correctness_evidence`; `P07.acceptance_bundle` | **Covered; evidence pending.** Passing technical tests alone does not establish business acceptance, provider qualification or production readiness. |
| C34 | Success criteria and explicit exclusions/open decisions; S1 success and boundaries; S2 §§8–9 | P01 acceptance/scope, P07 measurement/support, P10 costs, Master decision/gate registers | **Covered; decisions pending.** Keep quality, time-to-useful-answer, adoption and cost-per-accepted-answer measures distinct. Targets, baseline, language support, business definitions and authority must be resolved explicitly. Writebacks, unrestricted joins, autonomous actions and unapproved forecasting remain outside the accepted scope. |
| C35 | Approved analytical content and accountable approval/lifecycle behavior; S2 §§4, 9 | `P03.policy_decision`, `P03.lifecycle_disposition`, conditional `P03.selected_enforcement`; P04 publication | **Covered; selected enforcement is conditional.** Preserve accepted trace-only behavior and distinguish classification from execution policy. Missing evidence is not invented expiry; a new enforcement policy requires an actual owner decision. Do not rebuild accepted 2F.1 work. |

## 5. Recommended corrections before task generation

### REC01 — Make user/capability administration explicit in P10

Product §§2/8 and Master §3.1 already require this function. P02 supplies the authority to administer; it does not itself provide the administration workflow.

The smallest correction is a bounded P10 deliverable for application-level organization/user capability entitlements and enabled capabilities. A possible new output name is `P10.service_administration`, but this is a proposal only. The current documented register contains 46 named outputs; adopting a new output requires an explicit register/count/crosswalk update. Alternatively, an existing P10 output must be deliberately broadened and its ownership made unambiguous.

Acceptance should demonstrate an authorized administrator inspecting and changing supported entitlements, disabled/revoked behavior, isolation and safe audit. It must show that entitlement changes cannot grant underlying business-data permissions. Capability release/enablement is distinct from content publication and infrastructure deployment.

Required inputs are the applicable enforced P02 scope and P07 event contract. Actual cost metering should not unnecessarily block basic administration. Keep DEP15's metering prerequisite scoped to measured showback and applicable budget decisions.

### REC02 — Prove administrator-visible information under P07

The current documents already provide telemetry, support and metering foundations. Add a view/report acceptance matrix tying Product §8 to existing P07 outputs and the selected presentation surface.

For each enabled feature, identify the signal producer, permitted aggregation, counting rule, visible field, authorized viewer and evidence. Cover health/latency/failures, quality/unsupported outcomes, usage and relevant delivery status. Use an approved enterprise monitoring surface where appropriate; this review does not require building a new custom dashboard.

Keep P07 responsible for basic operational visibility. P13 consumes permitted aggregates for content improvement; it should not become a prerequisite for initial operational support.

### REC03 — Carry the pre-save schedule preview into P12

Add the frequency preview and conditional estimated-cost behavior to `P12.schedule_contract`. Include provenance/limitations when an estimate is available. If evidence is insufficient, show that the cost is unavailable rather than zero.

Record the selected P07 metering and P10 showback/allocation/price inputs at the consumer-activity level when estimates are offered. Preserve DEP19's allowance behavior for actual execution. Do not make all of P10, or an always-available estimate, a prerequisite for every scheduling activity.

### REC04 — Complete the analytics producer/consumer links

Refine DEP20 for `P13.improvement_proposals` so each chosen owner analytic identifies its permitted P07 usage/outcome/clarification or feedback inputs. Feedback alone does not demonstrate frequent-question, unsuccessful-search or repeated-clarification analytics.

Also link `P09.publication` IDs/versions to the appropriate permitted P07 usage observations. Acceptance should show both useful aggregates and protection against disclosure of another user's protected content. Publication remains reviewed; analytics cannot directly rewrite production definitions.

### REC05 — Carry existing behavior into task acceptance

Include the details in C01–C04, C06, C12–C14 and C18–C20 when decomposing the owning outputs. The Master already contains much of this behavior. The correction is to preserve it through task generation, not to invent new scope.

Each generated task should cite the product clause and Master revision/section, its delivery Plan and output, applicable engineering phase/slice, required inputs, testable user/system outcome and evidence location. Retain the full lineage through canonical Task/PR, acceptance evidence and release. Existing task identities must be reconciled before new ones are created.

## 6. Missing values versus missing scope

The following are legitimate unresolved inputs or evidence, rather than reasons to claim that the product is absent from the plan:

| Input or evidence | Owning area / disposition |
|---|---|
| Approved Deposits definitions, calculations, edge cases, reference answers and reviewers | `P01.reference_cases`, `P01.acceptance_owners`, `P04.semantic_bundle`. Synthetic fixtures can support framework development but cannot substitute for business sign-off. |
| Per-provider/environment identity, connector route, permissions and readiness | Applicable P02 route records and `P07.provider_readiness`. SQL evidence cannot qualify Databricks. |
| Named business/content/security/operational approvers and release authority | P01 and Master decision/gate records. Role names are not assigned people. |
| UI/question languages, selected richer report interactions, export treatment/size/distribution and additional formats | Product decisions and relevant P05/P09/P14 scope. Excel/PDF are already specified in P14. Persian documentation alone does not commit the application to Persian UI or queries. |
| Retention/deletion periods, permitted context/model payloads and preference controls | P02/P06/P08 plus applicable Master privacy/lifecycle decisions. Retention values must not be fabricated. |
| Scheduling stale-data policy, channels, timezone rules, recipients and owner-departure treatment | `P12.schedule_contract` with accountable policy owners. Test framework behavior against explicit synthetic policy fixtures where appropriate. |
| Cost unit prices, currency/effective dates, allocation rules, workload baselines and approved limits | P07/P10. Preserve unknown values and distinguish estimates from reconciled observations. |
| Performance, reliability, concurrency, freshness and support thresholds | P01/P07 and Master readiness gates. Specify owners and measurement methods before claiming acceptance. |
| Operative application Master/ADRs, current tasks/PRs, implementation and deployment evidence | Reconcile in a connected application session before adopting proposed mapping or creating duplicate work. Missing access is not evidence of failure or absence. |

The user also requested developer/project observability and future Copilot governance. Those are delivery-system requirements. They should be represented in the team execution framework, with explicit task/PR/evidence links, but their absence from the end-user Product Definition is not a product-coverage defect and does not justify an invented P16.

## 7. Preserved constraints

- Keep Master requirement/revision → engineering phase/slice → delivery Plan → named output → canonical Task/PR → acceptance evidence → release.
- P01–P15, Master engineering phases, detailed 2F slices, provisional 2G, executive Phases 1–3 and releases R1–R4 remain separate namespaces.
- Keep SQL and Databricks baseline scope across P01/P02/P04/P05/P07. P15 covers further expansion.
- Preserve App Service SQL system-assigned managed identity and application-enforced end-user authorization. Qualify Databricks separately.
- Retain historical successful login and SQL identity validation. Do not reopen those investigations without current regression evidence.
- Preserve existing worktrees, uncommitted changes, tasks/PRs and any newer Master candidate. No source plan was edited for this review.
- No saved prompt was executed; no issue, workflow, permission change, merge or deployment was performed.
- Keep conditional dependencies conditional. Only applicable unmet hard input dependencies should become execution blockers; shared contracts and approval gates are not interchangeable with them.

## 8. Next smallest justified activity

Prepare one planning-only amendment incorporating REC01–REC05 into the maintained portfolio and lineage reference, together with a product-clause-to-output acceptance matrix. Start with the P10 administration output decision, P07 visible acceptance and P12 preview contract; carry the remaining existing clauses into their owning outputs.

This is maintenance of the affected existing Plans, not a new delivery Plan. Its source prerequisites are the reviewed product/Master versions and the current output/dependency register. A connected application baseline is required before adopting revised engineering mappings or generating canonical implementation issues; it is not required to draft the planning amendment.

Acceptance evidence for that amendment:

1. Every applicable Product Definition clause has an explicit owning output, testable acceptance or recorded conditional/decision-pending disposition.
2. Administration, monitoring, owner analytics and schedule-preview dependencies identify the particular producer output and consuming activity, without whole-Plan overblocking.
3. Any new output is deliberately approved and reflected consistently in the output count, portfolio, lineage and task template; existing canonical identifiers are preserved.
4. No business values, people, dates, approvals, implementation status or deployment evidence are invented.
5. The connected-session reconciliation later links existing implementation/tasks before deciding what new work is actually needed.

Only after this correction and baseline reconciliation should the Copilot task/issue-generation prompt be finalized for execution. Do not generate speculative detailed implementation tasks for all 15 Plans at once; preserve later Plans at the appropriate outcome/contract depth until their inputs and scope justify decomposition.
