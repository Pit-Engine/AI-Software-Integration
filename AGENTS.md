# Agent instructions

Read [PROJECT_INSTRUCTIONS.md](PROJECT_INSTRUCTIONS.md) before starting framework or integration work. It is the project charter and defines the full workflow. For application work, also read the target repository's instructions and the relevant integration notes.

## Repository boundaries

- Identify the framework repository and the target repository or development workspace before editing. Record the target revision when it is available.
- Keep application code, adapters, interface changes, data, and tests in the target project. Do not copy or vendor them here. If the target workspace is unavailable, report the blocker and continue any useful assessment with the material available.
- Use this repository for independently testable shared components, integration instructions, and reusable findings. Use small synthetic examples and link to the target revision where appropriate. Propose changes to shared architecture for review.

## Integration workflow

1. Inspect the target's existing workflows, entry points, data formats, tests, and conventions before proposing changes.
   During inspection, also look for ambiguous outcomes and unexpected domain phenomena using [the diagnostic case assessment guidance](docs/integrations/ambiguous-result-assessment.md). Identify discriminating checks and potential benchmarks, not just ordinary happy paths.
2. Present selectable options based on the target, with tradeoffs, a recommended starting point, and explicit acceptance criteria. Proceed with substantial implementation once the user has chosen or already authorized the scope.
3. Use the application's existing entry points and preserve normal operation. Keep numerical calculations and validation in deterministic code. Follow the charter for permissions, previews, and approvals.
4. Verify the new behavior against the acceptance criteria and check the affected existing workflows. Report which tests ran and distinguish observed results from assumptions and open questions.
5. At a meaningful milestone, hand back the target revision, scope, test evidence, limitations, and lessons that could help the next integration. Use the [full workflow](PROJECT_INSTRUCTIONS.md#7-mandatory-workflow-for-individual-software-integrations) for the handoff details.

Keep credentials out of code, commits, fixtures, and logs. Use approved providers and data, and validate model outputs before they can affect application state.
