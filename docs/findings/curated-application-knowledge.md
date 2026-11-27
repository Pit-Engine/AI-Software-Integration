# Curated application knowledge: initial integration pattern

Status: Stage 6 local prototype; offline checks passed, live model evaluation pending.

Application terminology may differ from textbook conventions. Generic model knowledge, even when correct in a narrower domain, can misrepresent the actual program. Consult current release documentation and distinguish documented implementation behavior, physical theory, validated scope and unavailable results. Older notes may describe superseded behavior.

Begin with compact, source-grounded, versioned knowledge entries (stable ID, source document, section, release, note). Select a bounded number locally according to the question and eligible follow-up context. The initial target uses keyword matching and a maximum of three cards from nine curated entries, without embeddings, arbitrary filesystem reads or extra model calls. This is a baseline, not full-document search; missed matches, fixed-order truncation and limited paraphrase/language coverage remain risks. Prefer adding more sophisticated retrieval only after measuring failures.

Expose the knowledge count in the request confirmation and the exact selected notes in the outgoing preview. Keep permission and data minimization unchanged. Inform the model to distinguish supplied release knowledge from general knowledge and actual computed results; cite source document names for application-specific claims, and do not invent source access. Keep capability help synchronized with the prompt. Curated material is not independent scientific validation.

Record selected knowledge IDs and version in normal interaction events, with full request content only in optional diagnostics. This separates retrieval failure (relevant note missing) from reasoning or response failure (note present). Evaluate both relevant and unrelated questions, ambiguous terminology, scope limitations, unsupported questions and follow-ups; verify no invented citations and no leakage of arbitrary local files.

The first target's Stage 6 passed 62 AI unit tests and 25 Tk GUI/loader checks using offline/mocked transport. Also added combined local history export preserving prior unexpired session files, original session IDs and sequences, with diagnostic exclusion by default. No automatic history transmission, opt-in and retention unchanged. The solver numerical code was not modified, full numerical regression not rerun. Live model and Windows testing remain outstanding.

Target-specific notes, retrieval implementation, and logs stay in the local application. Only generalized methodology is proposed here; defer shared retrieval abstractions until evidence from multiple applications.
