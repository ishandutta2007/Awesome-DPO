# Safety Guardrail Hardening

DPO secures model outputs against adversarial prompt injection and jailbreaks.

## Workflow / Architecture

```mermaid
flowchart TD
    JailbreakPrompt[Jailbreak Input] --> SafetyDPO[Safety-Aligned Policy]
    SafetyDPO --> Refusal[Preferred Safe Refusal]
    SafetyDPO -->! HelpHarm[Suppressed Dangerous Content]
```

## Detailed Description
During red-teaming, safety alignment developers compile datasets of adversarial prompts. DPO trains the assistant to prefer safe, polite refusal paths over dangerous instructions or compliant jailbreaks.

[Back to README](../README.md)
