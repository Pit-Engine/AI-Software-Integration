# Application knowledge and maintenance

Status — Proposed integration guidance for review. Use the [project charter](../../PROJECT_INSTRUCTIONS.md) to select the workflows the assistant will support. Scale the following deliverables to that scope and keep the application-specific material with the application.

## 1. Guide to supported workflows and limits

For each supported workflow, record the application version, its purpose and prerequisites, and the steps using the visible menu, panel, and control names. Explain which settings, inputs, and outputs matter, including units and defaults. Distinguish what the application accepts, what has been validated, and what the assistant can currently see or do. Explain known limitations and how to recognize an incomplete or unavailable result.

For connected programs, trace the actual handoff from the originating action through the files or API to the downstream program and its observable result. Record the relevant program and format versions and conventions, such as units, coordinates, phase, or sign. Cite the current application source or documentation so the guidance can be checked. [Curated application knowledge](../findings/curated-application-knowledge.md)

## 2. Maintenance checklist

When a change affects a supported workflow, check the corresponding assistant guidance in the same change. Common triggers include renamed controls, changed defaults or units, revised file formats or external tool versions, new solver limitations, and changes to the assistant's context or available actions.

- Update the affected workflow guidance, knowledge entries, and examples against the new behavior. Mark any superseded version where users still need older guidance.
- Rerun a representative assistant question or guided workflow and the affected deterministic application or interoperability check. Include an unsupported case when the supported scope changes.
- Record the application revision, evidence, and any remaining coverage gaps in the application's release notes or integration handoff.

## 3. Research and verified domain examples

Research the domain around the workflows the assistant actually supports. Prepare short, versioned references that link to authoritative sources and explain their assumptions, applicability, and how they map to application terminology, settings, file formats, and outputs. Check that the assistant can retrieve the relevant entry for realistic user questions.

For a workflow where a plausible-looking setup can be wrong, pair the reference with a known-good runnable example and an independent check. Record the input, expected observable, tolerance where applicable, and how to reproduce the check. For a travelling-wave export, for example, first compare the reconstructed field with the reference field under the target program's phase and scaling conventions. Then compare the tracked particle response. Record any step that remains unverified.

Use the [workflow evaluation checklist](workflow-evaluation-checklist.md) to choose representative and ambiguous cases. The framework can share these templates and evaluation methods. Each application owns its guidance, research references, examples, and tests.
