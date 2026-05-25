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

The cream-cheese drawer case should be read as a positive OOD-composition example when the video shows the policy picking the cream cheese and placing it in the drawer. Cream cheese is an official LIBERO object, but this drawer target combination is not one of the 130 official benchmark instructions.

The `put the bowl on the plate`, `put the bowl on the stove`, and `put the bowl on top of the cabinet` instructions are official LIBERO instructions in other tasks, but in this report they are run inside the fixed `libero_goal/task_id=3` environment. They should be read as cross-task relation probes rather than the current task's official benchmark instruction.

## How to Read Results

| Field | Interpretation |
|---|---|
| `manual check=pass` | Human inspection confirms the current instruction was followed. |
| `manual check=fail` | Human inspection shows the current instruction was not followed. |
| `manual check=pending` | The video is included, but this case still needs manual labeling. |
