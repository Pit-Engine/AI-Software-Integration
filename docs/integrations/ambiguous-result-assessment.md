# Investigating ambiguous results and unexpected domain phenomena

Status: proposed integration assessment guidance, motivated by first-target live feedback; Stage 7.2 local prototype verified offline (2026-11-27).

## Why actively seek these cases during integration

A scientific or engineering application can return a numerically accurate result that is physically misidentified, incomplete, or surprising. Conversely a warning, recovered point, classification gap or abrupt trend need not be a numerical failure. The waveguide user reported a past apparent cutoff subsequently understood as a mode-tracking difficulty involving coupled modes. This is user-reported experience, not an independently reproduced benchmark. In the recent sweep the user considers two branch terminations consistent with cutoff and sees no numerical error; the available diagnostics alone do not settle the physical explanation.

## Proposed addition to the integration assessment

During inspection and opportunity discovery (charter steps 1–2), actively identify application-specific cases in which:

- A normal-looking output or successful status can conceal a semantic, physical, numerical or workflow problem.
- An unexpected output or warning can be normal behavior, successful recovery, or a valuable domain phenomenon.
- Multiple plausible causes have similar observable signatures; an inexperienced user or model may mistake one for another.
- A small, targeted follow-up calculation, comparison, inspection or experiment could distinguish competing explanations.

Seek examples in existing tests, validation reports, issue history, troubleshooting notes, code and authorized user experiences. Ask domain experts for genuinely difficult examples when appropriate. Do not invent incidents or assume all unusual results indicate problems. Record the available evidence, possible explanations, discriminating checks, and limits of the evidence. Propose useful read-only diagnostic or investigative assistance before execution; include difficult and ordinary cases in acceptance criteria. Keep specific incidents and sensitive data in the target environment.

## Four independent assessments

1. Numerical correctness: residual, convergence and independent reference checks.
2. Identity: whether the intended branch, object, configuration or operation was evaluated.
3. Domain interpretation: plausible physical or application-specific explanations.
4. Evidence sufficiency: which explanations are supported, ruled out or unresolved.

Distinguish observed facts from hypotheses. Avoid both false alarms and unwarranted assurances. Recommend targeted checks based on evidence rather than listing every possible failure. In numerical mode tracking, examples include local grid refinement, neighboring branches, sweep direction and field continuity; no automatic claim that these resolve a particular case. Similar distinctions can be applied to other domains after inspecting their actual semantics.

## Stage 7.2: bounded historical result context

Target overlay based on 7.1.1 retains two earlier single-mode snapshots and one compact earlier frequency-sweep summary in process memory, independent of debug recording. Immutable originating inputs and operation IDs accompany the earlier results. Deterministic comparisons expose changed fields and arithmetic deltas; matching names do not prove branch identity and simultaneous changes do not establish causation. Identical cache reuse does not create another sweep record. Previous answers remain excluded after snapshot changes; simple comparison keyword retrieval is not general semantic context management. Existing capability preferences govern historical access; no new execution permissions. Explicit consent scope includes bounded earlier results. Full-grid discrete monotonicity counts exclude missing steps and do not establish continuous trends.

74 unit tests and six focused Tk tests passed, including real successive solves/sweeps, source exclusion and cache reuse. No live DESY or Windows test, full numerical regression or large-history performance benchmark. No solver algorithm changes. Keep target-specific code and data local. Next: evaluate ambiguous interpretation and historical questions live; collect reproducible difficult cases and normal controls before extracting shared components.
