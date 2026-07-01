# Reference-Free & Iterative Online Era

The latest frontier in preference optimization shifts from static offline datasets to online self-correction and reference-free architectures.

## Workflow / Architecture

```mermaid
flowchart LR
    ActiveModel[Active Model π_θ] -->|Generates| SelfSamples[Self-Sampled Outputs]
    SelfSamples -->|Scored by| Verifier[Automated Verifier / Compiler]
    Verifier -->|Creates| DynamicDataset[Dynamic Preference Grid]
    DynamicDataset -->|Refines| Optimization[Reference-Free Loss ORPO/KTO]
    Optimization -->|Updates| ActiveModel
```

## Detailed Description
Modern optimization approaches remove the need for a static dataset. The model generates responses at runtime, which are automatically verified (by a LLM-as-a-judge, compiler, or unit test) to create immediate chosen/rejected preferences. These are optimized on the fly, often without needing a reference model in memory.

[Back to README](../README.md)
