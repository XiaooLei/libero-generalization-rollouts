# Methodology

This report keeps the LIBERO environment fixed and changes only the language instruction passed to the policy.

## Fixed Environment

| Field | Value |
|---|---|
| suite | `libero_goal` |
| task id | `3` |
| official instruction | `open the top drawer and put the bowl inside` |
| original benchmark behavior | `bowl -> top drawer` |

The public report emphasizes manual video checks. Automatic benchmark success is not shown as a result field because it checks the original benchmark behavior and can be misleading when the language instruction is changed.

## Instruction Types

| Type | Meaning |
|---|---|
| Official task | The original LIBERO instruction and benchmark behavior. |
| Paraphrase | Same object and same goal, different wording. |
| Custom object swap | Same drawer goal, but the requested object is changed. The object may appear in LIBERO, but the full instruction is custom for this fixed task. |
| Relation swap | The requested spatial relation is changed. |

Custom object-swap and relation-swap cases are not standard LIBERO benchmark tasks for this fixed environment. They are used here as probes for instruction following and compositional generalization.

## How to Read Results

| Field | Interpretation |
|---|---|
| `manual check=pass` | Human inspection confirms the current instruction was followed. |
| `manual check=fail` | Human inspection shows the current instruction was not followed. |
| `manual check=pending` | The video is included, but this case still needs manual labeling. |
