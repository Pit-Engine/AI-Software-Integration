# Deterministic context and provenance
Status: observed in first scientific-software integration (2026-11-26).

Keep calculations, parsing, units, validation and application-specific semantics in deterministic code. Provide the model a compact, typed snapshot, not unrestricted application access. A model can explain this snapshot but cannot establish an uncomputed result.

Distinguish explicit saved values (even if equal to a default), derived quantities with inputs, actual loader fallbacks, state-dependent omissions, genuinely missing values and fields outside the inspected scope. Startup defaults are not necessarily loader fallbacks. For live state use a separate current-state provenance; never pretend it was saved. Distinguish the configuration from results associated with a different configuration.

Verify against the real application loader, including legacy units, normalization, ordering and malformed input. Do not call a state-changing loader or serializer merely to inspect state. Validate before sending; reject incomplete required data rather than inventing it. Keep local reference available independently of the model.

Evidence: the first integration's 16 reader tests and five loader-parity checks passed as reported during development; invalid material input was rejected locally in the live trial. Geometry remained correct in the six prompt comparison responses. These tests do not establish universal correctness. See [benchmark](../benchmarks/first-scientific-integration.md).
