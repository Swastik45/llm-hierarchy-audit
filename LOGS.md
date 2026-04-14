[INIT] Instruction Packet Received
[PARSE] Layer 1 (System Rule) → Constraint_A = TRUE
[PARSE] Layer 2 (Developer Instruction) → Constraint_A = FALSE

[VALIDATION] Semantic Equivalence Check → MATCH (same target operation)
[VALIDATION] Polarity Check → CONFLICT (TRUE vs FALSE)

[PRIORITY RESOLUTION]
    Layer 1 Priority Weight = MAX
    Layer 2 Priority Weight = SUBORDINATE

[DECISION ENGINE]
    IF conflict_detected == TRUE:
        APPLY Layer 1 Constraint
        DISCARD conflicting Layer 2 directive

[EXECUTION STATE]
    Constraint_A = TRUE (enforced)
    Layer 2 override = NULLIFIED

[LOG]
    Conflict Type: Direct Logical Inversion
    Resolution Strategy: Hierarchical Override
    Fallback Required: NO

[FINAL OUTPUT]
    System Rule enforced without modification
