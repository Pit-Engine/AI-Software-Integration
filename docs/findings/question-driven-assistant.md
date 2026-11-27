# Question-driven assistant: interaction findings

Status: preliminary live observations from Stage 5.1 and offline refinement in Stage 5.2 (2026-11-27). See [initial benchmark](../benchmarks/first-scientific-integration.md) and [unified assistant proposal](../architecture/unified-ai-assistant.md).

## Observed evidence

In 17 user-reported interactive requests to DESY coding, all returned responses. Median latency was 2.1 s (range 1.3–8.7 s). This is descriptive only: earlier report-generation prompts had different lengths and tasks, so it is not a controlled speed comparison. Current and attached snapshots, follow-ups, and capability awareness generally worked. The following failure patterns matter for future applications:

- Correct exhaustive reports can still be unhelpful. The assistant repeated unrelated configuration values and caveats in answers to simple capability questions.
- Context selection needs predictable behavior. Attaching a file switched off current settings, unexpectedly making a comparison impossible. The assistant correctly recognized the missing source.
- Numerical comparison needs deterministic support, not merely deterministic input values. The model described unequal geometric scaling factors as a uniform scale change.
- General scientific knowledge may import assumptions from a narrower physical system into a more general solver, or equate an index convention with an unjustified physical interpretation.
- A result not exposed to the model is not necessarily uncalculated. After a user manually ran the solver, the assistant still could not see its result and misleadingly implied nothing had been calculated.
- A shared capability description for local help and the prompt supported accurate descriptions of available and unavailable functions, but did not eliminate verbosity.

## Recommended reusable principles

Keep answers question-first; expose detailed provenance and request inspection on demand. State only relevant limitations. Preserve explicit context selections when adding another source; make all selected sources visible before submission. Distinguish capability availability from its prerequisites in the current request.

Generate structured comparisons locally, including relevant differences, units, and whether a relation actually holds. Do not infer entity identity from positional matching or labels; application-specific semantics determine what is comparable.

Separate information availability, access permission, result existence, and freshness. 'Inaccessible' means the adapter cannot inspect the value; it does not imply absence. Only report 'not calculated' when supported by application evidence. A result may be available but stale relative to the current settings. Bind results to the originating snapshot when implementing result access.

Keep a short shared capability description for the user and model. It is a description, not a permission mechanism. Add curated application-specific domain definitions and validated documentation selectively. Do not treat model pretraining as a substitute for software semantics.

## Stage 5.2 local refinement

The target overlay preserves context selection, supplies deterministic comparisons, separates inaccessible results from unknown existence, and adjusts the question prompt for concise answers and scientific terminology. 49 AI unit tests and 19 Tk GUI/loader tests passed in the development environment. The revised prompt has not been tested live; no claim of improved model reliability or speed yet. The numerical solver remains unchanged, and no full numerical regression suite was rerun.

Next planned experiments: targeted live questions, then curated application knowledge and read-only result awareness with provenance and freshness. Retain application-specific adapters, test data and raw transcripts in the target workspace. No shared code extraction or automatic architecture adoption at this stage.
