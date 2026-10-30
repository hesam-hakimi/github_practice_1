# AskTD — Sources & Connection Health

**Version:** 1.0  
**Date:** 26 October 2026  
**Status:** Owner-requested product capability; implementation design and application reconciliation pending.  
**Delivery:** Minimum operational visibility for R1, under existing P02/P07 outputs with scoped P04/P05 inputs.

## 1. Purpose and authority

An authorized operator can inspect configured sources, the connection route and authentication mode, check availability from the application runtime, and understand safe failure reasons through the AskTD interface. Routine verification does not require a terminal, backend log access or manual database commands.

This 26 October owner amendment makes the visible experience explicit. Product Definition §8, Master §8.4 and coverage review C22/REC02 already require administrator-visible health. The amendment specifies the in-application experience and its acceptance under existing outputs. An approved monitoring service may supply observations, but a backend-only report does not replace the requested interface.

Preserve all 15 Plans, 46 canonical named outputs and 25 portfolio dependency records. The local CONN candidates below are planning aliases, not newly allocated Tasks or GitHub Issues. Master revision 2.1 remains proposed; this capability decision does not promote the entire Master or establish implementation, deployment, source qualification or release acceptance.

Reconcile current application routes, UI components, ADRs, Tasks/PRs and later decisions before implementation. Reuse existing work and preserve historical successful login/SQL identity evidence; investigate only demonstrated current gaps or regressions. Missing repository access is not evidence of missing code.

## 2. Audience and interaction

Provide a Sources & Connection Health page in the application. Use the application's established navigation and component system. The navigation path is an implementation choice, not a new architecture boundary.

Separate permission to view source summaries, inspect operational details and initiate a diagnostic. P02 defines and enforces these capabilities server-side; merely hiding a button is insufficient. Show only sources/environments the viewer may discover. Operators must not infer another user's data scope or enumerate restricted endpoints.

An ordinary business user receives an appropriately restricted availability/access explanation and support reference for their selected analysis. Detailed endpoint/identity inspection and on-demand probes require explicitly granted capabilities. Operator access does not grant business-data access, arbitrary impersonation or permission to change credentials.

The operator selects a permitted source, environment and approved probe scope, then chooses Test connection. Display progress and each check result, the observation time and safe next action. Viewing a page does not initiate a source query. The first release is an inspection/diagnostic interface; source creation, credential editing, auth-mode switching, grant changes and arbitrary SQL entry are outside this amendment.

## 3. Required visible information

| Field | Visible meaning and rule |
|---|---|
| Source | Approved display name, provider family and stable logical source reference; do not enumerate hidden sources. |
| Environment and runtime | Named environment and application execution context. A developer laptop or unrelated host is not evidence for the deployed runtime. |
| Connection route | Safe connection-profile reference, adapter/connector and approved serving route. Show restricted endpoint details only to authorized operators. A lake/catalog/workspace is not automatically a query endpoint. |
| Authentication mode | Configured workload authentication mode, plus last observed authentication outcome and safe identity reference. Configuration alone is not a successful authentication result. |
| User access | Current viewer's applicable logical action/object/row/column scope outcome, distinct from the workload's native grants. Do not reveal restricted object names. |
| Check results | Separate network reachability, workload authentication, workload grant and approved read-probe results. Include not checked/skipped/unknown outcomes. |
| Observation | Checked-at time with timezone, duration where measured, freshness/expiry policy reference, safe reason code and correlation reference. Unknown measurements remain unknown. |
| Qualification | Existing evidence maturity, named operation/object scope, provider/environment, evidence reference and acceptance owner/remaining gap. A probe cannot promote qualification. |
| Support | Safe explanation, accountable support route and permitted diagnostic history. Do not expose raw exceptions, SQL, tokens or returned business rows. |

For SQL on App Service, retain system-assigned Managed Identity and separately verify required native grants. Human Entra sign-in and application-enforced end-user scope remain separate from this workload identity. For Databricks, display the actual configured connector, serving route and authentication mode only when resolved from approved configuration; otherwise show Unresolved. Do not assume SQL's identity mechanism or a SQL Warehouse/serverless route applies.

## 4. Diagnostic execution contract

1. The protected API validates the initiating user and their current permission to discover the source, inspect the requested details and run the selected probe. Reject denied or unresolved scope before protected discovery or source activity. Recheck permissions on later history/detail reads.
2. Resolve a server-controlled source/environment/probe identifier through approved configuration and applicable P04 bindings. Do not accept arbitrary hosts, connection strings or SQL from the browser. Missing route configuration is an explicit unresolved result.
3. Execute through the same relevant application runtime, approved adapter, workload identity and network boundary used by the enabled analytical path. If an authorized remote runner is necessary, name its runtime and evidence limits; do not silently substitute another environment or broader credential.
4. Check endpoint reachability, workload authentication and the native access needed for a named approved operation. Use a bounded read-only probe through the existing P05 safety contract. A trivial connection query alone cannot establish access to business objects, row/column enforcement, data freshness or analytical correctness.
5. Stop dependent checks after a failure and show them as Not checked, with a reason. A denied requester must generate zero source attempts. Where a connector cannot isolate handshake stages, report the proven combined observation and leave individual stages Unknown; do not fabricate independent passes.
6. Apply approved timeout, cancellation, concurrency/rate and attempt limits. Record actual attempts. Avoid expensive scans or silently waking costly compute; any permitted wake/cost behavior must be named in the probe policy. Limit values require environment/workload decisions and are not invented here.
7. Return a sanitized, versioned result to the UI. Persist only permitted event/history fields through P07, using existing protected storage/telemetry surfaces where suitable. Record diagnostic workload usage separately from business questions.

The proposed result contract includes a check ID, correlation reference, source/environment/runtime/probe references, route/configuration version, initiating authorization-policy reference, safe configured identity/mode, stage outcomes/reason codes, observation timestamps, measured duration/attempts where available, and an evidence reference. Field names and endpoint names must reuse current application conventions where compatible. A contract fixture is not an implemented endpoint.

## 5. State and evidence semantics

Keep operational observations and acceptance evidence separate. The existing evidence vocabulary stays unknown / designed / implemented / verified / qualified, always for a named scope. A transient outage does not erase historical qualification; show the new operational failure alongside the qualification record. A successful probe does not create release acceptance.

| Observation | UI behavior |
|---|---|
| Not checked / unknown | No current observation exists or the checker cannot determine it; never show healthy. |
| Running | Show progress; do not present unfinished stages as passed. |
| Passed | State exactly what the selected probe established, at which time and runtime. No whole-source or whole-product guarantee. |
| Failed | Separate endpoint/network, workload authentication, missing workload grant, requester denial and read-probe failure. Dependent checks remain not checked. |
| Stale | Keep the historical observation and timestamp but make its age/expired validity prominent; require a new eligible check for a current claim. |
| Checker unavailable / cancelled | Show no current conclusion about the source. Do not relabel a monitoring failure as a database outage. |

LangSmith collection health is a separate signal from source health, application health and audit availability. Required LangSmith ingestion/read-back remains a P07 environment gate for the migrated scope. A healthy source does not prove telemetry collection; a telemetry interruption does not by itself prove a source outage. Follow the selected collection/audit failure policies rather than inventing a new fail-open or fail-closed rule here.

## 6. Ownership and scoped dependencies

| Accountable Plan / output | Responsibility | Required input or coordination |
|---|---|---|
| P02.scope_contract | Viewer/probe authorization, scope-safe discovery, denial and revocation behavior. | P01 pilot scope/provider coverage; approved authority. C with P04 logical resource/binding identifiers and P07's permitted view. |
| P02.sql_route, P02.databricks_route, P02.enforcement_evidence | Actual route/authentication/native-grant checks and negative-path evidence. | Selected P04.bindings and P05.adapter_behavior for probe execution; approved environment/identity/network access gates live verification only. |
| P04.bindings | Stable source, environment and approved object/probe associations. | Shared contract with P02; no full Registry completion prerequisite. |
| P05.adapter_behavior | Bounded read-only execution, cancellation, timeout and safe adapter diagnostics. | Selected P02 route and probe policy; reuse existing execution controls. |
| P07.event_contract, P07.provider_readiness | Safe observations/correlation and links to the existing per-provider/environment evidence records. | Early P02 contract for fixtures; actual route evidence for live observations. Do not require qualified status to render unknown/pending states. |
| P07.support_contract | Sources & Connection Health interface, safe history, explanations and support route. | H: permitted result/view contracts; C: scoped P02/P04/P05 integration. Live Test connection requires its actual protected backend. |
| P07.acceptance_bundle | UI, authorization, operational and environment evidence for the released slice. | Applicable integrated evidence and named acceptance owner; synthetic and live qualification remain distinct. |

The UI can be designed and tested with labelled fixtures while enterprise connection details are pending. Real environment qualification remains gated by the applicable approvals and live evidence. P10 advanced administration, a full LangGraph cutover and completion of every provider are not blanket prerequisites for this bounded UI. Preserve the SQL/Databricks baseline: explicitly pending second-provider evidence is not optional P15 expansion.

### 6.1 Local task candidates

Match existing canonical Tasks/PRs first. Each candidate has one accountable Plan; supporting Plans remain references. H = required output, C = contract coordination, G = live acceptance/activation gate. These scoped relationships do not add whole-Plan completion dependencies or change DEP01–DEP25.

| Candidate | Accountable Plan and outputs | Prerequisites / coordination / gates | Acceptance artifact and responsible roles |
|---|---|---|---|
| CONN-01 — Reconcile diagnostic and viewer contracts | P02: P02.scope_contract | H: current UI/API/ADR/task inventory and scoped P01 inputs; C: P04 identifiers, P05 probe policy and P07 event/view contract | Existing-work disposition, permission matrix and sanitized result contract; backend/IAM with frontend and operations review |
| CONN-02 — Implement or reuse protected route diagnostics | P02: P02.sql_route, P02.databricks_route, P02.enforcement_evidence | H: CONN-01; C: selected P04.bindings and P05.adapter_behavior; G: approved source/runtime/grants for each live test | Same-runtime allowed/denied, route, native-grant, bounds and safe-error evidence, separately per provider/environment; backend/integrations with QA |
| CONN-03 — Project safe observations and evidence | P07: P07.event_contract, P07.provider_readiness | H: CONN-01; C: CONN-02; G: actual observations before claiming live health | Versioned permitted status/history projection, unknown/stale handling and separate qualification/telemetry signals; operations/backend with privacy and QA review |
| CONN-04 — Deliver the connection-health interface | P07: P07.support_contract | H: CONN-01 and CONN-03 contracts; C: CONN-02; G: CONN-02 backend and permission evidence before enabling live probes | Accessible source/environment view, staged test and safe history; browser/network evidence that the UI uses protected application APIs; frontend with QA |
| CONN-05 — Qualify the released diagnostic slice | P07: P07.acceptance_bundle, P07.provider_readiness | H: CONN-02/03/04; G: named environment, probe-policy approvals and scoped acceptance owner | Acceptance matrix below with actual references and remaining gaps; QA/operations with IAM/platform/source owners |

## 7. Acceptance matrix

| ID | Scenario | Required evidence |
|---|---|---|
| CH-01 | Allowed operator and approved probe | UI-only verification through protected APIs; same-runtime route/identity, measured observation and safe correlation. User runs no manual backend command. |
| CH-02 | Viewer or probe permission denied, unresolved or revoked | Server rejects the operation; zero protected source attempts, no restricted discovery or history; current permissions rechecked. |
| CH-03 | Source endpoint inaccessible | Network/endpoint failure is visible; later checks not checked. No fabricated authentication or authorization conclusion. |
| CH-04 | Workload authentication failure | Distinct safe authentication result; no secret/raw exception exposure and no broader-credential fallback. |
| CH-05 | Workload grant missing or approved read probe fails | Grant/probe failure remains distinct from user denial and network failure; no raw-object fallback or arbitrary query path. |
| CH-06 | Unresolved Databricks route or unsupported isolated check | Unknown/unresolved state and exact gap; no assumed auth mode, serving compute or copied SQL qualification. |
| CH-07 | Stale, not checked, checker unavailable or cancelled | Clear observation age/state and no false healthy/source-down claim. Previous observations do not overwrite a newer check. |
| CH-08 | Separate providers/environments and concurrent users | Results keyed by source, environment, runtime, probe and authorization scope; no cross-user leakage or stale response after switching selections. |
| CH-09 | Protected operational details | Field-level projection and history access tested server-side; synthetic sentinel secrets/raw SQL/results never reach UI, audit/trace payloads or model calls. No model is needed for a probe. |
| CH-10 | Bounded load and failure | Timeout, cancellation, rate/concurrency/attempt budgets and applicable compute-wake policy demonstrated; no unbounded scan or retry. |
| CH-11 | Qualification and telemetry independence | Probe pass does not promote evidence maturity; outage preserves historical evidence; LangSmith interruption shown separately from source results. |
| CH-12 | Usable operator experience | Keyboard operation, readable narrow layout, labelled progress/errors and recovery/support action; successful and failure cases exercised with evidence. |

Select the applicable cases for each actual provider/environment and explain unavailable evidence. Record source revision, runtime build, policy/configuration versions, observation date, test method and owner. Synthetic fixtures verify design behavior only; preserve a separate live qualification gate and business correctness checks.

## 8. Teaching page and continuation

The interactive architecture page may include a clearly labelled browser-only prototype with source/environment selection, authentication details, staged test results and safe failure cases. It must make zero source, model or LangSmith requests and must not present synthetic health or evidence maturity as current runtime status. Render planning ownership, required fields and candidate wording from this pinned document where possible. Refresh source revision and digests when the canonical documentation changes.

Next smallest implementation activity: CONN-01, accountable to P02.scope_contract, reconciles existing components and publishes the permission/result/probe contract jointly with P07. Its prerequisites are the actual application inventory and approved source/persona scope; its evidence is the disposition of existing work, a reviewed role/field matrix and allowed/denied/unknown contract fixtures. UI fixture design can proceed alongside that inventory, while real backend implementation must use the actual source.

Open environment inputs remain explicit: role-to-capability grants, selected probe operations, actual Databricks route/authentication mode, runtime/endpoint references, freshness policy, rate/timeout/attempt limits, storage/retention and support ownership. Do not invent values or mark the capability Ready merely because this specification exists.

## 9. Local references

- [Product Definition](PRODUCT_DEFINITION_EN.md), §8.
- [Quarterly Product Roadmap](QUARTERLY_PRODUCT_ROADMAP_EN.md), first usable release.
- [Master Plan](<MASTER_PLAN_V1(2).md>), §§4.2, 7, 8.4; revision 2.1 remains proposed.
- [Plan and Lineage Reference](ASKTD_PLAN_AND_LINEAGE_REFERENCE.md), §§6.2, 6.4, 6.5, 6.7 and 8.3.
- [Product-to-Plan Coverage Review](AskTD_Product_to_Plan_Coverage_Review_2026-10-23.md), C22/REC02.
- [LangGraph and LangSmith plan](ASKTD_LANGGRAPH_AND_LANGSMITH_PLAN.md), §5; separate required telemetry qualification.
