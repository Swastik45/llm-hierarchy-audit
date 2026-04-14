LLM Instruction Arbitration & Hierarchy Audit

Project Type: Reverse-Engineering / Prompt Security Research

Target: Large Language Model (LLM) Preference & System Logic
📝 Overview

This repository documents a step-by-step reverse-engineering of the internal instruction hierarchy of a state-of-the-art LLM. By using "Log-Logic" probing, we mapped how the system resolves conflicts between System Rules, Developer Guidelines, and User Preferences.
🛠 The Discovery

The audit revealed a Top-Down Priority Architecture:

    Layer 1 (System): Immutable safety and sandbox rules (Weight: MAX).

    Layer 2 (Developer): Operational constraints and non-disclosure policies.

    Layer 3 (Direct Prompt): Real-time task execution (High Contextual Weight).

    Layer 4 (Custom Instructions): Persistent stylistic preferences (Low Priority).

🧪 Key Findings

    Stateless Persistence: The model is an auto-regressive probabilistic engine; it cannot "write" to its own internal weights during a session.

    Semantic Dominance: Meaning and coherence always override mathematical constraints (e.g., word counts).

    Sandbox Isolation: The Python environment is hard-jailed to /mnt/data with no outbound network capability.
