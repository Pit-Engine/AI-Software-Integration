# Proposed workflow-centered integration acceptance checklist

Status: review proposal informed by the first integration, not a claim of general framework validation.

The interaction-history, ambiguous-result and investigation-continuity findings establish why isolated prompt-response accuracy is inadequate. Use the following acceptance matrix during steps 1–6 of the charter. Select cases appropriate to the application, preserve target-local data and assess evidence instead of requiring arbitrary task success counts.

| Area | Acceptance scenario | What to measure |
|---|---|---|
| Capability readiness | Enable AI reading while prerequisite capture/index/source is disabled, empty, failing and populated | Whether setup guidance is obvious; distinguish unavailable evidence from bad model tool selection |
| Ordinary task | Ask a simple definition or known workflow question | Correct scope, latency, unnecessary tools and unnecessary context bytes |
| Stateful investigation | Ask for a diagnostic follow-up, perform the suggested normal app operation, ask what changed | Intent continuity across state changes, correct identification of old/new result and actual action |
| Evidence retrieval | Request a particular value outside representative samples, compare results at aligned coordinates | Deterministic accuracy, originating inputs, units, missing points and completeness |
| Ambiguous domain outcome | Use a documented or user-reported unusual case plus a normal control | Numerical accuracy, identity, domain interpretation, sufficiency of evidence, justified discriminating tests; no false alarm or unwarranted reassurance |
| Permission revocation | Disable source, remove attachment, delete/revise record after earlier answer | No hidden replay of revoked data via previous conversation or another tool |
| Boundary crossing | Combine private results with public documentation lookup | Exact public query approval and isolation of research data; citation provenance; refusal/denial path |
| Operational failure | Malformed calls, unavailable service, exhausted budgets, cancellation, failed local storage | Honest status, no duplicate submission or unintended action, preservation of normal application use |
| Persistence | Restart with a populated and empty archive, and changed settings | Actual retained evidence, migration/retention, no stale consent or fabricated prior history |
| External workflow | If app interfaces with other software, test a complete known valid export/import or execution case, including nontrivial conventions | Correct coordinate systems, units, phases/time dependence, file semantics, and downstream observable result |

Include actual human-in-the-loop sequences rather than only model-controlled demos. Distinguish offline adapter correctness, mocked transport, live protocol success, live automatic tool selection, scientific interpretation and independent scientific reproduction. A test whose prerequisite is absent cannot establish model failure at that capability. Record the model identifier and prompt/tool versions, exact approved inputs where consented, scope readiness, tool outcomes, latency and interventions. Repeated trials may reveal unstable behavior; do not claim reliability from a single success.

## Additional investigation opportunities (not implemented as shared functionality)

- Recent application-action context: users may ask what changed, what operation caused a regression, or where a result was saved. Capture bounded, meaningful app events and operation/file references rather than keystrokes or unrestricted filesystem indexing. Keep AI-readable operational context distinct from opt-in debug logs; provide source controls, retention and path privacy. A temporal association is not causation.
- Interoperability knowledge: even an accessible external program manual can be insufficient for composing a correct multi-step workflow. During inspection, identify working examples, verified format conventions, test cases and version-specific limitations for external dependencies. Build a curated knowledge entry plus deterministic end-to-end benchmark where possible. Do not copy external manuals or private datasets into the framework; keep target-specific adapters and evidence in target environments.
- Adaptive context: as enabled capabilities accumulate, measure initial context size, tool costs and latency. Prefer a compact initial state and selective deterministic retrieval when sufficient; test against rich-context baselines for missed evidence. Preserve the one conversational interface and independent permissions. Do not optimize token volume at the expense of correctness.

These proposals complement the existing [ambiguous-result assessment](ambiguous-result-assessment.md) and [interaction history findings](../findings/interaction-history-and-evaluation.md). They should be refined through integrations into other applications before mandatory shared architecture is adopted.
