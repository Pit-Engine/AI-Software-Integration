# Interaction history and human–AI evaluation

Status: proposed reusable methodology, with an initial local implementation in the first target integration (Stage 5.3, 2026-11-27). No shared code or mandatory architecture adopted.

## Motivation
A conversation alone may not explain why a user request failed: selected context, available capabilities, previous application operations and approval decisions matter. A user's initial difficulty can be a normal learning process, not necessarily an interface defect. Evaluate recovery and task completion over time, and distinguish observations from inferences about user intent. User feedback remains essential.

## Minimal event journal
Use a versioned structured append-only format such as JSON Lines. Include session ID, timestamp, event sequence, event type and correlation IDs for requests and application operations. Record relevant events, not arbitrary keystrokes or mouse movement. Separate:
1. Conversation: questions, answers, model/prompt version, latency, request outcome.
2. Interaction: context selection, attachment events, help usage, approvals, application operation start/end, observed snapshot changes. Clearly state which events are actually captured and whether the journal is incomplete.
3. Optional diagnostics: exact approved request payload, relevant context and tool/validation metadata when implemented. An approved or started request is not proof of provider receipt. A missing completion event alone is not proof of failure.

Persistent history for evaluation is independent of bounded model conversation memory. Do not automatically transmit history to the model.

## Privacy and control
Recording should be explicit, local by default, visibly indicated and stoppable. Make detailed diagnostics a separate opt-in. Avoid logging credential fields, authorization headers, unnecessary paths or raw provider exceptions. Questions and answers themselves can contain sensitive data; do not promise automatic redaction. Offer a reviewable export, deletion, bounded storage and retention. Exported copies may be outside managed retention. Failures of optional recording must not impair normal software or AI interaction. No automatic publication of application-specific logs in the framework.

## Evaluation methodology
Classify observed issues with evidence and uncertainty: user learning, interface predictability, discoverability, model reasoning, domain knowledge, context management, unavailable capability, technical failure, ambiguous intent. Allow multiple or uncertain classifications. Separate task success, correctness, attempts, recovery, unnecessary repetitions, latency, interventions and capability demand. Do not minimize message count as a goal by itself; valuable scientific follow-up can be lengthy. Compare repeated use and user feedback before concluding that an initial error indicates bad design.

## First target evidence and implementation
Stage 5.2: five user-reported live answers correctly addressed earlier nonuniform comparison, mode-index semantics, inaccessible-result wording and capability questions; repetitive caveats remain. Small sample, no general reliability claim.

Stage 5.3: the target's local assistant now has opt-in session JSONL recording, context and request events, selected file and single-mode-operation events, separate diagnostic capture and reviewed JSONL/text export. Default retention 30 days (7/30/90 selectable, pruning on start), 5 MiB per session. No new solver-result access or model-memory behavior. Only observed snapshots and selected operations are recorded; not a complete application replay. Local storage is not encrypted by the feature. 56 AI unit tests and 24 actual Tk GUI/loader checks passed, including mocked API/operation outcomes. New recording interface not yet tested live on Windows; full numerical regression not rerun. The implementation and any logs remain in the target workspace.

Next: collect consented natural-use traces, assess recovery and task completion without over-attributing user error, and iterate the schema only when evidence supports it. Test portability in another application before extracting a shared recorder or evaluation engine.
