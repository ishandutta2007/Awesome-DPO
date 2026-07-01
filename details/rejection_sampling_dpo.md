# Rejection-Sampling DPO

Rejection-Sampling DPO filters candidate generations to feed high-signal training pairs to DPO.

## Workflow / Architecture

```mermaid
flowchart TD
    Prompt[Prompt] --> SampleN[Generate N Candidates]
    SampleN --> Scorer[Score/Filter via Verifier]
    Scorer --> SelectExtreme[Select Best y_w and Worst y_l]
    SelectExtreme --> DPOTrain[DPO Training Step]
```

## Detailed Description
For each prompt, the model samples multiple responses. A scorer filters the best and worst outputs, creating maximum-margin preference pairs. This focuses the training signals on clear distinctions, speeding up convergence.

[Back to README](../README.md)
