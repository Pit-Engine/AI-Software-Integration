# Read-only assistant integration pattern
Status: initial pattern demonstrated; recommendations subject to further testing.

1. Identify target revision and application read paths; keep implementation in target workspace.
2. Build and test pure context adapter. Validate schema and distinguish state provenance. No writes, calculations delegated to model, or unrestricted file reads.
3. Use a small replaceable provider interface. For DESY, the initial client used an authenticated chat-completions endpoint and model identifier coding, bounded request/response sizes, timeout, no redirects/retries, and existing Windows encrypted credentials or private manual entry. Do not commit or log secrets. Verify institutional permission for each data type.
4. Show exact outgoing content and destination; require explicit consent. Keep data and credentials separate. No tool execution; untrusted content is not instruction authority.
5. Keep request work off the GUI thread; marshal results back to UI. Prevent duplicate in-flight requests, distinguish hiding from cancellation, and handle errors without affecting normal software.
6. Keep deterministic reference and generated text separate; mark scientific output unvalidated. Test invalid input, cancellations, authorization, failure, state preservation, and responsiveness with simulated transport, then live synthetic tests.
7. Benchmark multiple independent live responses and assess scientific semantics; obtain user feedback about usefulness. A correct exhaustive report can still be a poor assistant.
8. Return generalized findings and reference the target artifact/revision, not copies of its code or datasets. Extract reusable code only after evidence of portability.

Initial target had no Git repository; its baseline was the 2026-10-22 Library archive version 7 and local cumulative overlays Stages 1–4. Stage 4 changed only the GUI entry point among original files according to development comparison. Live GUI trial succeeded; full numerical suite was not rerun. The target-specific implementation, fixture and logs remain local.
