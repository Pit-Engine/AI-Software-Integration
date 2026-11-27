# Simulation result provenance and freshness

Status: Stage 7 local prototype, offline verification completed; live model evaluation pending.

## Reusable principles

A result is not the current configuration. Capture the actual immutable numerical inputs at launch (including method and numerical controls), identify the operation and its outcome, and bind returned quantities to that snapshot. Capture values in explicit units and represent complex quantities structurally. Compute derived numerical quantities deterministically using the originating inputs, not edited UI values. Preserve the difference between a requested tolerance, an observed residual, a solver-reported status and independently established accuracy.

Track the latest attempt separately from any retained result. A running, failed or cancelled operation may leave an earlier result intact; a no-root outcome is not proof of physical cutoff. Do not attach an untracked result to current parameters. Read-only result adapters must not execute additional simulations or alter the numerical object.

Compare current solve inputs locally with the originating inputs; report matching, different, unknown or not applicable. Exact equality is a conservative initial approach, not proof of physical equivalence or convergence. Distinguish inaccessible results, confirmed absence within the inspected scope, and results that exist but are stale. Do not infer absence of other results from a limited adapter.

Expose result selection and originating settings clearly in the approved request. Result snapshots can contain sensitive information even when current settings are deselected. Preserve the normal/diagnostic recording distinction: record result status, freshness and operation IDs in normal events, full payload only in optional diagnostic events. Exclude outdated follow-up context when source snapshots change.

## First target observation and verification

The target GUI displayed a derived quantity using the currently entered frequency even when showing an older retained solution. This was corrected locally to use the solved frequency. This illustrates how AI integration can uncover pre-existing provenance defects in ordinary application workflows.

The Stage 7 overlay exposes an opt-in last single-mode result source, with captured launch inputs, latest attempt, retained result, complex propagation constant and effective index, phase velocity, observed current-amplitude modal power and available solver-reported diagnostics. It does not expose sweeps, fitting, full fields or persistent results from prior application sessions. No numerical solver modifications.

65 AI unit tests and 27 Tk GUI/loader tests passed. Two new GUI tests include real closed vacuum-waveguide solves compared to analytical effective index and phase velocity, normalization, matching/different/unknown freshness, and mocked running/cancel/no-root transitions. Full numerical regression, Windows testing and live provider evaluation remain outstanding. Exact-input comparisons may conservatively mark numerical-control or display-only changes as different. No cross-application portability claim.

Next: evaluate natural interaction with real results and extend the read-only adapter to additional result types only after evidence supports it. Keep all application-specific implementation and data in the target workspace.
