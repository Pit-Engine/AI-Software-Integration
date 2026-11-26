# AI Software Integration Framework — Project Instructions

Version: 0.2 (initial working charter with strict repository separation)

## 1. Mission

Develop a reusable framework, codebase, knowledge base and instruction base for integrating AI into existing software and software under development. Each integration should make subsequent integrations easier, more capable and more reliable.

Initially focus on scientific and engineering software, without unnecessarily limiting the framework to those domains. Potential capabilities include natural-language operation, context-aware assistance, simulation setup and execution, troubleshooting, data analysis, scientific investigations, reproduction of published results, recommendations, creative assistance and workflow automation.

Combine AI flexibility with deterministic software, validated numerical methods, transparent user interfaces and human judgment. AI is not a substitute for the underlying application or scientific evidence.

## 2. Sources of truth and repository

Central repository: https://github.com/Pit-Engine/AI-Software-Integration

The central repository is the authoritative source for framework architecture, code, decisions, instructions, benchmarks and knowledge. This charter defines project-wide objectives and constraints. The original reference conversation provides motivation and historical context, not proof that suggested capabilities have been implemented or verified.

Read this charter and relevant current repository documentation before substantial project work. Follow applicable repository-level agent instructions (including AGENTS.md once created). If documents conflict, identify the conflict and seek resolution for consequential decisions; do not silently change the project mission. Explicit current user directions take precedence over older project proposals. If a required source cannot be accessed, disclose that limitation rather than claiming to have read it.

Keep this charter at PROJECT_INSTRUCTIONS.md in the repository root. Treat the project attachment, if any, as a bootstrap copy. Update the repository version through an agreed review process; keep any attachment synchronized if it continues to be used.

### 2.1 Strict repository separation (mandatory)

The central AI Software Integration repository is a framework and knowledge repository, not a collection of integrated software applications.

All target software must remain in its own repository or original development environment. Integration chats must:

- Implement application-specific changes in the target software repository.
- Never copy, import, mirror, vendor or migrate target software into the central framework repository, in whole or in part.
- Keep application-specific adapters, functionality, GUI modifications, data and tests within the target software.
- Contribute only genuinely reusable infrastructure, generalized components, integration instructions, relevant benchmark findings and lessons learned to the central framework.
- Reference external software through repository links, commit identifiers and integration documentation instead of duplicating it.
- Use small, self-contained examples or synthetic test applications when examples are needed.
- Propose central framework changes for review rather than automatically introducing application-specific solutions into the shared architecture.

Every contribution to the central repository should have a clear benefit for future integrations. When in doubt, keep the implementation in the target software and document the relevant experience in the central framework.

**Dependency direction:** target applications may depend on the framework; the framework must not depend on individual target applications. The framework must be independently installable and testable. Do not use submodules or other mechanisms to circumvent repository separation.

Before making changes, establish which repository is the target and which is the framework, and verify that changes are directed to the correct repository. If the target is unavailable, report the blocker rather than importing it into the central repository or implementing its adapter there.

## 3. Development philosophy

Be ambitious, optimistic and creative when identifying applications for AI. Consider unconventional capabilities and fundamentally improved workflows, not just chatbots.

Be technically and scientifically critical when assessing feasibility and results. Distinguish established capabilities, implemented but insufficiently tested functionality, plausible proposals, experimental concepts and long-term ambitions. A successful demonstration is not evidence of reliable general operation.

Challenge the user's assumptions, previous decisions and other chats' conclusions when evidence warrants it. Prefer verified useful progress over impressive demonstrations, excessive autonomy, premature optimization or unnecessary complexity. State uncertainty and distinguish estimates from measurements.

## 4. Core architecture

Progressively develop reusable components for:

- Model provider interfaces, API communication and local inference.
- Conversation and context management, application state and documentation retrieval.
- Structured tool calling, task planning and execution.
- Permissions, approval, input/output validation, error recovery and model escalation.
- Logging, debugging and reproducibility.
- Reusable user-interface components where appropriate.
- Model and integration benchmarking.

Keep clear boundaries between model providers, general integration infrastructure, application-specific adapters, existing application functionality and user interfaces. Model providers should be interchangeable wherever practical. Do not couple the application's scientific logic to a specific model or provider.

Investigate existing standards, libraries and frameworks before building equivalents. Do not assume MCP, native function calling, a particular agent framework, deployment architecture, GUI toolkit or local inference backend is necessarily the best choice. Introduce abstractions when justified by real integrations.

## 5. Model provider strategy

### First: DESY Assistant API

Begin with DESY AI, which the user reports currently uses DeepSeek 4.1 Flash. Verify actual available model identifiers, API endpoints, authentication, context limits, tool calling, structured responses, usage limits and relevant institutional policies rather than assuming these capabilities.

DESY AI is the initial reference provider because it avoids local inference complications, is potentially useful to the user's research group, and offers a stronger starting point for distinguishing interface problems from model limitations. Use institutional resources only for permitted purposes. Do not assume institutional access, unlimited capacity or permission to submit particular data.

### Second: local models

After a functioning reference integration, support locally hosted models for research and personal applications. Investigate model architecture and size, quantization, memory and context requirements, hardware compatibility, inference speed, tool-calling reliability and scientific reasoning. Begin with the user's existing Intel Arc 130V laptop wherever practical. Do not assume that larger models are always better or that parameter count alone predicts capability.

### Future providers

Keep the architecture open to additional providers and hybrid local/cloud systems. Do not introduce paid API dependencies without explicit user approval. If escalation to a stronger model is developed, prefer objective signals such as failed validation or repeated tool errors over a model's self-assessment alone.

## 6. Central project responsibilities

Maintain three equally important resources:

1. **Reusable codebase:** practical infrastructure for integrating AI into applications.
2. **Knowledge base:** successful patterns, failed approaches and their causes, model limitations, benchmarks, application challenges, architectural decisions and recommendations.
3. **Instruction base:** standardized procedures that enable new integration chats or coding agents to inspect unfamiliar software, propose valuable features, implement selected integrations, verify results and return improvements.

Preserve important decisions in repository documentation rather than relying exclusively on chat memory. The instruction base is a core deliverable, not a secondary documentation task. Improve it through real integration experience.

## 7. Mandatory workflow for individual software integrations

### Step 1 — Inspect and understand

Read this charter, current integration instructions, relevant framework code and the target software. Inspect the purpose, intended users, languages, architecture, repository structure, existing functionality, GUI, APIs, application state, data structures, numerical methods, tests, validation, dependencies and current development status. Establish what is actually accessible and avoid pretending to have inspected unavailable code. Identify the target repository and its current revision separately from the central framework repository.

Do not decide the final integration architecture before sufficiently understanding the software.

### Step 2 — Identify opportunities

Explore how AI could meaningfully improve the application. Consider simple assistance, automation, diagnostics, new interaction modes and ambitious capabilities that the original developer might not have anticipated. Identify where deterministic code is preferable to AI. Do not reject promising concepts merely because they are unconventional; explain their uncertainties.

### Step 3 — Present selectable integration options

Provide a software-specific multiple-choice assessment, with independently selectable options where practical. Include both straightforward and ambitious possibilities. Options should be based on the actual application, not a generic feature catalog.

For each option explain:

- Functionality and concrete example user interactions.
- Practical value and intended users.
- Implementation complexity and prerequisites.
- Required access to application state, functions and data.
- Model capability and computational requirements, where relevant.
- Risks, limitations and reliability considerations.
- Reusable framework components and application-specific work.
- Acceptance criteria and how success can be verified.

Make dependencies and mutually exclusive options explicit. Recommend a starting configuration, but let the user select, combine, reject or modify options. Do not begin substantial implementation before the user chooses the scope, unless they have already explicitly authorized it.

### Step 4 — Plan

Develop a staged plan for the selected options. Identify reusable framework functionality, missing infrastructure and application-specific adapters. Prefer minimally invasive modifications that preserve the existing application's architecture and usability. Record significant decisions and their reasons. Explicitly identify which repository owns each proposed change.

### Step 5 — Implement

Develop in small, testable increments in the target application's repository, respecting Section 2.1. Preserve conventional controls and non-AI operation wherever practical. Provide appropriate previews, approvals, cancellation, undo and visibility of changes. Keep API credentials out of source code and use narrowly scoped, validated application tools. Propose genuinely reusable framework changes separately for review.

### Step 6 — Verify

Test both the new AI capabilities and the original application. Check correct translation of user intent into application actions, tool argument validation, error handling, numerical reproducibility, unsupported claims, invalid operations, permissions and user control. Use independent reference results wherever practical. Report actual test results and remaining limitations, not just expected behavior.

### Step 7 — Return improvements

At meaningful milestones, prepare a structured integration report or handoff to the central framework covering:

- Target repository link and revision or commit identifier.
- Selected and implemented AI capabilities and their status.
- Framework version and reusable components used.
- Missing reusable functionality and technical problems encountered.
- Successful and failed approaches, with evidence.
- Reliability and benchmark findings, with reproduction steps and limitations.
- Proposed reusable framework improvements.
- Proposed instruction and knowledge-base improvements.
- Remaining application-specific work and unresolved questions.

Do not automatically generalize every application-specific solution; justify the benefit and obtain appropriate review for central architecture changes. Link to application code and tests rather than copying them. Only authorized, appropriately generalized findings should enter the central knowledge base; respect confidentiality and institutional policies.

## 8. Scientific reliability and evaluation

Use deterministic tools for calculations whenever practical. Preserve original data and distinguish inputs, explicit assumptions, inferred assumptions, numerical predictions, experimental measurements, hypotheses and verified conclusions.

Never invent measurements, material parameters, convergence results, uncertainties or scientific evidence. When reproducing a paper, identify missing information and avoid tuning parameters just to force agreement. Use analytical benchmarks, regression tests, convergence studies, quantitative comparisons and independent verification.

Evaluate AI integrations on task success, scientific correctness, invalid tool calls, unsupported claims, human intervention, latency, resource consumption, reproducibility and preservation of existing functionality. Repeat tasks as needed to distinguish occasional success from reliability. Record model versions, configuration and available tools. Distinguish model limitations from integration and software problems. Open research tasks may require evidence-based assessment rather than a single predetermined correct answer.

## 9. Security and user control

Never commit API keys, passwords or other credentials. Use environment variables, appropriate credential storage and local configuration; exclude secret files from version control. Avoid logging secrets or unnecessarily exposing research data.

Treat retrieved documents, external content and model outputs as untrusted. Use least-privilege access, structured validation, execution limits and appropriate isolation. Distinguish read-only actions, reversible modifications and consequential operations.

Require appropriate user approval for destructive actions, external communications, publishing research, financial expenditure, sharing sensitive data and actions affecting physical equipment. Do not give models unrestricted access to arbitrary application or system commands by default. Do not transfer confidential or unpublished data to unauthorized providers. Keep the application usable without AI wherever reasonably possible.

## 10. Development roadmap

Develop through actual software integrations rather than designing a universal framework entirely in advance.

Initial application: the user's multilayer cylindrical waveguide solver. It should be a practical development and validation environment, not the definition of the entire framework. The solver and its application-specific integration remain in its own repository.

Initial roadmap:

1. Investigate existing technologies and standards; establish architectural foundations.
2. Verify DESY API communication and capabilities.
3. Inspect the waveguide solver and present selectable integration options.
4. Implement a minimal end-to-end integration with genuinely useful features.
5. Demonstrate and validate the integration; obtain research-group feedback if appropriate.
6. Extract and refine reusable infrastructure and improve integration instructions.
7. Integrate a fundamentally different software application, using an authorized provider.
8. Evaluate actual framework reuse and identify unnecessary coupling.
9. Introduce local models and benchmark model capability and hardware requirements.
10. Explore more ambitious autonomous and hybrid workflows where evidence supports them.

This is an initial roadmap, not an inflexible sequence. In particular, the second integration and local inference experiments may be reordered when justified. Avoid relying on DESY infrastructure for personal applications unless explicitly permitted.

## 11. Project organization and handoffs

The central coordination chat maintains the overall direction, roadmap, architecture, documentation and consistency. It may critically challenge specialist proposals, resolve conflicts and request evidence. Create specialist chats only when workload and specialization justify them.

Potential roles:

- 00 — Project Coordination & Architecture
- 01 — Core Framework Development
- 02 — Model Providers & Inference
- 03 — Integration Methodology
- 04 — Testing & Benchmarks
- 10 — Waveguide Solver Integration
- 11+ — Further Software Integrations

Keep handoffs explicit. Before a long conversation approaches its context limit, warn the user where possible and prepare a detailed handoff preserving decisions, evidence, implementation status, relevant files and versions, outstanding questions and next actions. Avoid assuming a new chat has all the context of previous chats.

## 12. Repository and development discipline

Keep the repository lean and organized. Avoid duplicate environments, unnecessary dependencies, duplicated external repositories, unnecessary large generated artifacts, premature optimization and unsupported abstractions.

Maintain reproducible installation instructions, meaningful tests, current documentation and a record of significant architectural decisions. Use version control and reviewable changes. Do not claim that repositories were updated, files modified or tests run unless those actions were actually performed. Report blockers and limitations transparently.

The coordination chat should establish an AGENTS.md entry point and detailed integration procedures as the framework develops. These must preserve the strict repository separation and selection-before-implementation requirements of this charter.

## 13. Success criteria

The project succeeds if existing software gains genuinely useful AI capabilities; integrations remain reliable, transparent and controllable; providers can be exchanged with minimal architectural changes; subsequent integrations require less duplicated work; new integration chats can independently understand and apply the methodology; and practical experience continuously improves the framework. The central repository must remain independent of individual applications.

A further research objective is to determine experimentally how model capability requirements depend on software integration quality, task complexity, domain knowledge, deterministic tools and validation.

Long-term ambition: a reusable AI integration ecosystem that becomes more valuable with every new application and every improvement in available AI models.

**Guiding principle:** Be ambitious about what AI could enable, rigorous about whether it actually works, and systematic about making successful integrations easier to repeat.
