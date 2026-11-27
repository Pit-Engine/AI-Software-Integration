# Unified AI assistant
Status: proposed architecture for review; not a framework implementation (2026-11-26).

User feedback after a working configuration-report GUI: the output was overwhelming; the user wants to ask a particular question about an attached file or something visible in the program, receive a direct answer and useful optional context. Separate capability-specific menus are not a natural primary interaction.

Prefer a single visible, collapsible input area with Help-menu access, a conversation surface, visible source selection and optional attachments. Preserve comprehensive reports when explicitly requested. Keep detailed provenance, reference facts and outgoing request preview accessible on demand, rather than forcing a full report for each question. A user can use normal software controls without AI.

Proposed stages:
1. Question-driven, read-only assistant: current configuration snapshot, optional selected saved file, bounded follow-ups; clear source distinction; explicit submission consent; nonblocking transport. No arbitrary filesystem, tools or solver execution.
2. Context-aware help: selected GUI element, curated documentation, then result snapshots tied to their originating configuration.
3. Capability registry and coordinator: select narrowly scoped deterministic functions via natural language. Separate permissions for inspection, reversible changes, simulation and consequential operations. Validate tool arguments, show previews, ask approval where needed; never execute arbitrary model text.

Provider stays independent of app context and UI. The application owns state adapters and action implementations. Context selection should be explicit and minimal; do not silently attach entire state/history. Capture immutable request snapshots and indicate staleness. Do not conflate model capability selection with authorization.

Open questions: layout across different applications, context budget and selection, how to manage follow-up history without stale data, response verification, and whether one abstraction works across a second application. No shared architecture is adopted automatically; validate in target environments before extracting infrastructure.
