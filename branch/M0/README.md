# M0 Working Pack

**Status:** Working draft based on repository documents; no customer, equipment, or safety decisions are approved by this document.
**Prepared:** 2026-10-07
**Purpose:** Make M0 manageable by separating what the documents say, what can be prepared now, and what a human decision owner must provide.

## Start here

M0 is a discovery and decision-tracking milestone, not a request to build the production inspection system. The immediate goal is to establish what the system is expected to inspect, how an inspection should proceed, who owns each decision, and what evidence is needed before implementation contracts are treated as stable.

The repository contains demos and planning documents, but the reviewed material does not identify an approved customer requirements baseline, named decision owners, or accepted performance limits. Therefore:

- Treat the workflow below as a **draft for review**, not a specification.
- Treat simulator behavior and displayed values as **demo evidence only**.
- Leave a decision open when its owner or evidence is unknown. Do not fill gaps with guesses.
- Keep production implementation in an explicitly approved production workspace. The repository guidance describes this repository and its `docs/` folder as local analysis/reference material.

## What I could prepare from the available material

These are bounded M0 activities that do not require authority to make customer or equipment decisions:

1. Read and inventory the linked JIG2, 3-axis, and milestone documents.
2. Separate planning proposals and demo observations from approved requirements.
3. Record source discrepancies and known unknowns rather than selecting a preferred answer.
4. Draft a generic inspection lifecycle and an initial decision/evidence checklist.
5. Identify likely owner roles and mark every unconfirmed owner as **owner-unassigned**.
6. Prepare questions and evidence requests for the first review with the project lead and relevant human owners.

This pack is that initial preparation. It does **not** claim that the M0 exit gate has passed.

## Evidence labels used in this pack

| Label | Meaning |
|---|---|
| **Documented** | Explicitly stated in a reviewed document; this alone does not mean approved. |
| **Demo-observed** | Behavior or values represented by a repository simulator; not a real-machine requirement or integration result. |
| **Proposed** | A planning recommendation or draft workflow that needs review. |
| **Unresolved** | The reviewed material does not answer the question, or evidence conflicts. |
| **Approved** | Formally confirmed by the accountable human owner with a traceable source. No customer/equipment decisions are marked approved here. |

## Source inventory and limits

| Source | What it contributes | Status / limit |
|---|---|---|
| [Integrated delivery milestones and repository split](../../docs/5_delivery-integration-milestones-and-repository-split.md) | Shared M0–M5 proposal, scope boundaries, dependencies, and recommended logical modules. | Final planning proposal, but customer requirements, owners, dates, and acceptance thresholds still require approval. |
| [JIG2 software milestones](../../docs/3_jig2-software-milestone.md) | Draft M0 outputs and common software milestone expectations. | Draft; not evidence of approved customer requirements. |
| [3-axis-head software milestones](../../docs/4_3axis-head-software-milestone.md) | Proposed 3-axis extensions and G1–G5 checks. | Draft; equipment, coordinate, calibration, and acceptance details remain open. |
| [JIG2 implementation requirements analysis](../../docs/1_jig2-구현요구사항.md) | Analysis of the JIG2 HTML/Markdown demo, including simulator behavior and source discrepancies. | Analysis of a simulator, not a production specification. It notes differences between `jig2.md` and `jig2.html`, including versions and dimensions. |
| [JIG2 factory-delivery software scope](../../docs/2_jig2-공장납품-소프트웨어-구현범위.md) | Candidate software responsibilities and exclusions for a future factory-delivery system. | Candidate scope; target environment and customer interfaces are not confirmed. |
| [JIG2 versus 3-axis-head changes](../../docs/2a_jig2-대비-3축헤드-변경사항.md) | Demo comparison and additional 3-axis software questions. | Simulator comparison; it explicitly does not establish a depth camera, real axis control, or actual MES integration. |
| [Milestone handover index](../../docs/agent-handovers/README.md) | Assignment boundaries and shared guidance for M0–M5. | Repository guidance says `docs/` is local-only and production implementation belongs in an approved production workspace. |

### Evidence already visible

- **Documented:** The planning proposal recommends one shared M0–M5 sequence and treating 3-axis work as extensions if selected.
- **Documented:** Low-level machine control, interlocks, and safety belong outside the software team's assumed ownership; the interface and test boundary still need agreement.
- **Demo-observed:** JIG2 and 3-axis HTML pages visualize candidate sequences and controls.
- **Unresolved:** The authoritative product/process specification and current approved equipment configuration were not identified in the reviewed documents.
- **Unresolved:** The JIG2 analysis records version/dimension discrepancies between `jig2.md` and `jig2.html`; an authorized owner must identify the controlling source.
- **Unresolved:** Whether 3-axis is in scope is not approved in the reviewed sources.

## M0 task list: what a human needs to prepare

For each task, the first column describes the outcome. "Human input" is information or authority that cannot be responsibly invented from this repository. "Can be prepared now" is bounded analysis/documentation that can happen before those decisions arrive.

| Task | Human input or preparation needed | Can be prepared now |
|---|---|---|
| **1. Confirm scope and source of truth** | Project lead: identify the customer/project, the intended inspection station/product, the authoritative requirements and drawing revisions, and who may approve changes. Confirm whether JIG2, 3-axis, both, or neither is the target. | Inventory available files, report contradictions, and prepare an evidence register. |
| **2. Define the inspection unit and identifiers** | Process/customer owner: say whether one inspection is per PCB, assembly, panel, lot, or another unit; provide required product, serial, lot, process, station, and request identifiers, including where each comes from. | List candidate identifiers as questions only; draft request-to-result traceability needs. |
| **3. Describe the approved operator/process flow** | Process and quality owners: provide the current work instruction or a walkthrough from request/part arrival through final disposition and removal/next step. Identify operator actions and who handles exceptions. | Draft the neutral lifecycle below and mark each stage that needs confirmation. |
| **4. Define defects and disposition policy** | Quality/customer owner: provide defect names and definitions, reference images/examples if available, OK/NG/manual-review rules, borderline policy, severity, and who may override or release a result. | Create a placeholder taxonomy/register structure; do not set thresholds or labels. |
| **5. Decide reinspection and exception behavior** | Process, quality, and operations owners: state rules for reinspection, manual review, duplicate requests, invalid/missing inputs, timeouts, cancellation, operator pause, application restart, and recovery. Identify allowed retry counts/actions and audit requirements. | Enumerate scenarios and draft branches without choosing their outcomes. |
| **6. Provide data and acceptance evidence** | Data owner/customer: identify representative image/measurement data, labels and label definitions, data-use permissions, privacy/confidentiality restrictions, retention/deletion rules, and an authorized data-transfer method. Quality/customer owner: approve measurable acceptance and cycle-time targets plus how they will be tested. | Prepare a data/evidence checklist and distinguish AI performance from 3-axis metrology performance. No data should be copied or used until access is authorized. |
| **7. Confirm device, interface, and responsibility boundaries** | Equipment/controls owner: identify real camera/sensor/lighting/PLC/axis equipment and approved software interface documents, if any. Name who owns installation, low-level control, interlocks, safety, integration testing, and recovery. IT/MES owner: provide approved external interface specifications and test-environment access through the approved process. | Draft software boundary questions. Do not select devices/protocols, request credentials in this document, or prescribe machine motion. |
| **8. Resolve the 3-axis option, if applicable** | Project/equipment owner: explicitly select in-scope/out-of-scope/deferred. If in scope, provide sensor type/source and sample data; product/fixture handling; axes and coordinate frames/units; calibration owner and procedure; move/settle feedback; capture-inhibit conditions; approved recovery owner; and reference measurements/tolerances. | Maintain a separate 3-axis question list. Keep all unknown coordinate, sensor, and motion details provisional. |
| **9. Confirm target environment and operations** | IT/security/operations owners: provide target OS/network constraints, authentication/access rules, logging and data security requirements, installation/update method, storage/backup expectations, retention, support owner, and approved test location. | Draft the environment/operations decision list; defer deployment choices. |
| **10. Assign owners and close the M0 register** | Project lead: name one accountable decision owner for each open item and agree target milestone or due point. Each owner supplies a decision, evidence, or an explicit deferral reason. | Maintain status, source, impact, owner, evidence needed, and next action; summarize what blocks M1. |

### If you can only answer four things first

1. What exact product/station and project is this work for, and which document is the approved source of truth?
2. Is the target fixed-head JIG2, 3-axis, both, or undecided?
3. Who is the project lead, and who can approve process/quality and equipment/safety decisions?
4. Is there an authorized way to access representative requirements, drawings, work instructions, images, and interface specifications?

These answers unblock organizing the next review; they do not by themselves approve detailed requirements.

## Draft inspection lifecycle for review

This is a technology-neutral proposal synthesized from the milestone documents. It is **not** confirmed machine behavior.

```text
Inspection requested
  -> Identify inspection unit and validate request/required inputs
  -> [If approved 3-axis flow] receive measurement -> validate freshness/quality
       -> calculate approved target -> request upper-level move -> verify feedback/settling
  -> Acquire image/input -> validate input quality
  -> Run inspection/inference -> apply approved disposition policy
  -> Record result and evidence -> report/notify through approved interface
  -> Complete and make the inspection traceable
```

Candidate exception branches to confirm:

- Invalid or incomplete request/input -> explicit reject, hold, or operator action (decision open).
- Duplicate request -> defined idempotency/duplicate policy; do not assume it creates a second inspection.
- Measurement, capture, inference, persistence, or external-interface failure -> visible error state and approved retry/hold/recovery behavior.
- Borderline result -> manual review or another approved disposition; policy and authority open.
- Timeout, cancellation, stop, and restart -> define which state is persisted, whether work can resume, and who authorizes recovery.
- For 3-axis, invalid/stale measurement or unconfirmed axis state must not be treated as permission to capture; exact inhibit and recovery rules require equipment-owner approval.

## Initial decision register

All items below are **open** based on the reviewed material. "Likely owner" is a role suggestion, not an assignment. Where no named accountable person is known, status is explicitly **owner-unassigned**.

| ID | Open question / decision | Impact if unresolved | Likely accountable role | Evidence or approval needed | Target |
|---|---|---|---|---|---|
| D-01 | Which project/product/station and source-document revision is authoritative? | M0 scope and all downstream work can target the wrong process or configuration. | Project lead / customer owner — **owner-unassigned** | Approved requirement baseline, drawing/work-instruction revisions, written scope confirmation. | M0 |
| D-02 | Is the equipment fixed-head JIG2, 3-axis, both, or deferred? | Changes workflow, interface and verification scope. | Project lead / equipment owner — **owner-unassigned** | Explicit scope decision; if 3-axis, approved equipment concept and owner. | M0 |
| D-03 | What constitutes one inspection, and which identifiers are mandatory? | Contracts, duplicate handling, traceability, and reporting depend on it. | Process/customer owner — **owner-unassigned** | Process walkthrough and approved identifier/source mapping. | M0 |
| D-04 | What are the defect taxonomy, decision boundaries, borderline path, and override rules? | Incorrect or unauditable quality disposition. | Quality/customer owner — **owner-unassigned** | Approved defect definitions, examples, limits, review/override authority. | M0 |
| D-05 | What are the retry, reinspection, duplicate, timeout, cancellation, restart, and recovery rules? | Lost, duplicated, or unsafe-to-resume inspections; inconsistent operator guidance. | Process/quality/operations — **owner-unassigned** | Approved scenarios and role-specific recovery instructions. | M0 |
| D-06 | Which data may be used, where can it be stored, and for how long? | Data access, evaluation, privacy, and retention compliance. | Data/customer/IT owner — **owner-unassigned** | Written usage permission, transfer/storage controls, retention/deletion approval. | M0 |
| D-07 | What measurable quality, throughput, and cycle-time targets apply, and who accepts them? | No defensible verification or production-readiness claim. | Quality/customer owner — **owner-unassigned** | Approved numerical targets, measurement method, and sign-off role. | M0 |
| D-08 | Which camera/sensor/PLC/MES/ERP interfaces are real and approved? | Adapter scope and integration estimates remain speculative. | Equipment/controls and IT/MES owners — **owner-unassigned** | Interface specifications, boundary diagram, test endpoint/access approval. | M0–M1 |
| D-09 | Who owns equipment setup, low-level control, interlocks, safety, and integration/recovery tests? | Unsafe or unauthorized assumptions about software responsibility. | Equipment/controls/safety owner — **owner-unassigned** | Responsibility matrix and test/approval boundary. | M0 |
| D-10 | What target environment, security controls, operations support, and installation method are required? | Deployment and operation design may be incompatible with the site. | IT/security/operations — **owner-unassigned** | Site constraints, security requirements, support and recovery ownership. | M0–M1 |
| D-11 | If 3-axis is selected, what sensor, fixture, axes, coordinate frame/units, calibration, move/settle feedback, capture inhibit, and recovery policy apply? | Unsafe or invalid capture and untestable measurement-to-motion behavior. | Equipment/controls/metrology/quality — **owner-unassigned** | Approved device/interface and coordinate documentation, reference data, tolerances, calibration and recovery approvals. | M0–M1 / G1 |
| D-12 | Which JIG2 source revision governs where `jig2.md` and `jig2.html` differ? | Simulator details could be mistaken for the design basis. | Project/equipment owner — **owner-unassigned** | Written revision decision and, if relevant, controlled drawing/specification. | M0 |

## Initial scope and risk boundaries

### Candidate software scope to validate

- Inspection request handling, input validation, workflow/state tracking, operator-facing disposition and error status.
- Image/input validation, inference boundary, traceable result/history, and approved reporting/integration interfaces.
- Testable mock interfaces while real devices or external systems are unavailable.
- For an approved 3-axis option only: measurement validation, coordinate/calibration-aware upper-level sequencing, feedback checks, traceability, and capture inhibition as specified by the equipment owners.

### Not assumed to be software-team ownership

- Mechanical/electrical design or selection/installation/wiring of cameras, lighting, sensors, fixtures, PLCs, motors, or pneumatics.
- Low-level real-time machine control, interlocks, or safety design/approval.
- Customer acceptance, defect policy, data rights, or numeric quality limits.
- Actual MES/ERP/device integration until specifications, authorization, and test environments exist.

### Principal risks

1. **Demo-to-specification confusion:** simulator animations, values, and simulated MES statuses could be treated as production requirements.
2. **Unclear source of truth:** JIG2 documents differ in version and geometry details; no controlling revision is named in the reviewed set.
3. **Unowned decisions:** no named human approvers appear in the reviewed M0 planning materials.
4. **Unapproved data:** AI/metrology exploration cannot be meaningful or authorized without representative data/reference measurements and usage permissions.
5. **Unclear safety boundary:** application sequencing must not be confused with low-level motion or safety responsibility.
6. **3-axis uncertainty:** sensor identity/source, fixture/product handling, coordinate/calibration, feedback, and recovery remain open.

## Suggested review order

1. Project lead confirms scope, source of truth, and named decision owners.
2. Process and quality owners walk through one normal inspection and the important exception paths.
3. Equipment/controls/safety owners confirm the software boundary and, if selected, the 3-axis extension.
4. Data, IT/MES, security, and operations owners provide the evidence and constraints relevant to their decisions.
5. Record each item as approved, open with an owner/evidence/next step, or deferred with a reason.
6. Hand the stable and provisional items to M1; do not wait for unrelated decisions if M1 can produce clearly provisional examples and mock tests.

## M0 exit check

- [ ] Scope and source-of-truth revisions are identified, or explicitly open with an owner and next step.
- [ ] Inspection unit, identifiers, workflow, defect/disposition policy, and exception paths are approved or visibly unresolved.
- [ ] Requirements and decisions distinguish evidence, approval, assumption, and unresolved status.
- [ ] Every material open decision has an accountable named owner, evidence/approval needed, impact, and target milestone; otherwise it is explicitly owner-unassigned and escalated.
- [ ] Software/equipment/controls/safety/customer boundaries are reviewed by the appropriate owners.
- [ ] The fixed-head versus 3-axis choice is explicit, or 3-axis is deferred with a reason; its unknowns are not silently treated as fixed-head requirements.
- [ ] No simulator assumption is represented as an approved requirement, and no production performance or integration claim is made without evidence.
- [ ] M1 receives a concise list of approved inputs, provisional examples, and blocking decisions.

## Handoff to M1

Once the first human review supplies decisions, the next step is to label each requirement as approved, open, or deferred and produce a short M1 handoff containing:

- Stable request/result/status concepts and identifiers that M1 may use.
- Provisional examples that are safe to use only in mock fixtures.
- Open schema/interface choices and their named approvers.
- Approved data/label permissions and evaluation-plan constraints, if available.
- Verification scenarios and performance/security/operations decisions that remain blocked.

Do not create a production contract, choose device protocols, or implement machine behavior from this draft alone.
