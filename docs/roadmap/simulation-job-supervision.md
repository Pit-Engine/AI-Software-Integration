# Simulation job supervision

**Status** — Candidate for the first full build, after a simple integration proves the basic workflow.

Long-running simulations can fail hours after launch, and parameter studies can finish with missing cases. A supervisor could track progress, explain failures, and help recover or advance an approved batch. A small first integration should establish the model connection and demonstrate one useful application action.

## Detect the execution backend

Identify the backend per run from the application's launch configuration and available job metadata. A Slurm job ID tied to the configured cluster is useful evidence. A connection to a cluster login node alone leaves the job's execution backend unknown. Where the application supports both local and remote runs, retain the detected backend and the evidence used to identify it with the run record. This lets the user supervise a run without selecting the backend again. [DESY Maxwell job documentation](https://docs.desy.de/maxwell/documentation/jobs/)

## Stage the capability

1. Read job status and available progress signals. Report completed, failed, and outstanding cases. Distinguish scheduler state from simulation progress and explain what evidence supports a diagnosis.
2. Preview a recovery action. Report why a job stopped when the evidence allows, whether a compatible checkpoint is available, and what would change if the run were resumed or started again.
3. Apply a bounded retry policy to approved failure classes and submit remaining cases from a predefined batch. Persist run and attempt records so repeated checks or a supervisor restart cannot submit the same case twice. Require review before changing scientific inputs or solver settings.

An initial full-build demonstration should recognize one known backend and one run with insufficient evidence, report an ordinary running job and a failed job accurately, and explain a proposed recovery using the available records. Compare the assistant's diagnosis with the scheduler status, log, and checkpoint evidence. Application-specific code and fixtures belong in the target application's repository.
