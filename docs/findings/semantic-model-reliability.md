# Semantic model reliability
Status: preliminary experimental finding, 2026-11-26.

Correct numbers are insufficient if the model misunderstands their semantics. In the first integration an ambiguous internal index name resembled a physical derived quantity. The model sometimes conflated the two and reversed the definitions of two mode indices even when the numeric label was right.

Rename model-facing fields to domain-specific terms and explicitly define conventions; distinguish identifiers from measured or calculated physical quantities. Keep original and revised prompts versioned. Test exact requests repeatedly, assess meanings as well as numbers, and include missing-information and contradiction checks. Do not rely on model self-assessment. Keep a deterministic reference accessible.

In an alternating six-request diagnostic with the same synthetic configuration and DESY coding, manual core scientific assessment changed from 1/3 correct with original wording to 3/3 with revised wording. Two changes were combined, so their separate effects are unknown; small sample, no reliability guarantee. A revised answer also calculated a correct but unrequested ratio. Prompt controls are not an execution or validation boundary. See [benchmark](../benchmarks/first-scientific-integration.md).
