# Methodology

This report keeps the LIBERO environment fixed and changes only the language instruction passed to the policy.

## Fixed Environment

| Field | Value |
|---|---|
| suite | `libero_goal` |
| task id | `3` |
| official instruction | `open the top drawer and put the bowl inside` |
| original BDDL goal | `bowl in top drawer` |

The automatic LIBERO success predicate still checks the original BDDL goal. It does not change when the custom instruction changes.

## Instruction Types

| Type | Meaning |
|---|---|
| Official task | The original LIBERO instruction and BDDL goal. |
| Paraphrase | Same object and same goal, different wording. |
| Object swap | Same drawer goal, but the requested object is changed. |
| Relation swap | The requested spatial relation is changed. |

Object-swap and relation-swap cases are not standard LIBERO benchmark tasks. They are used here as probes for instruction following and compositional generalization.

## How to Read Results

| Field | Interpretation |
|---|---|
| `BDDL success=true` | The original `bowl in top drawer` goal was achieved. |
| `manual check=pass` | Human inspection confirms the current instruction was followed. |
| `BDDL=true, manual=fail` | The rollout satisfies the original benchmark goal but does not follow the current instruction. |
| `BDDL=false` | The original benchmark goal was not achieved; manual inspection is needed to evaluate the custom instruction. |
