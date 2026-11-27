# Structured knowledge and source presentation

Status: Stage 6 live observations and Stage 6.1 offline prototype, 2026-11-27.

## Evidence and limits

Six user-reported questions to DESY coding using the first curated library returned responses (2.0–4.3 s, median 2.5 s). The responses generally reflected the actual application, but one misapplied a branch-index mapping, one incorrectly generalized a material restriction across solver families, and the fitting explanation omitted the custom-weight qualification. The user's transcript was manually copied; recording was not enabled. Thus selected knowledge IDs and exact requests cannot be independently verified for this sample. No controlled comparison or general reliability claim.

These observations motivate changing the representation of knowledge, not merely retrieving more text. Encode enumerated support conditions as explicit matrices, nontrivial nomenclature as explicit mappings with scope/qualification, and weighted numerical definitions with equations and default assumptions. Use deterministic translations or checks when justified. Keep validated scope distinct from accepted inputs. Separate defects in the source material or adapter from model reasoning failures.

## Presenting sources

Internal application knowledge should normally be integrated into direct answers without showing implementation filenames. Preserve source metadata, release, IDs and exact selected notes in the inspectable request and optional diagnostic history. Provide internal sources when explicitly requested. External web research and published scientific claims, when such features are actually available, should retain useful externally inspectable citations. Never fabricate references or claim access not provided. These are presentation choices, not a removal of provenance.

## Debug history preference

The user considers recording a debug feature, not ordinary conversation memory. Preserve explicit recording opt-in across restart with a visible indicator and a distinct new session ID; an explicit stop persists the off state. Optional diagnostic consent and retention settings are included in that preference. Retain earlier unexpired files, allow combined review/export, and do not infer recording consent from the existence of old logs. No automatic transmission. Report storage failures; optional logging must not impair normal operation.

Stage 6.1 target implementation passed 65 AI unit tests and 26 real Tk GUI/loader checks with mocked transport, including explicit opt-in, restart, new session, prior log preservation and explicit stop across launches. Updated prompt and structured cards have not been tested live; full numerical regression and Windows testing remain outstanding. The local solver and its application-specific code and data remain outside the framework. Do not extract shared implementations until portability is evaluated.
