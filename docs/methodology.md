# Methodology

This report keeps the LIBERO environment fixed and changes only the language instruction passed to the policy.
The core test is whether a policy can follow object-target combinations that do not appear as exact instructions in the official 130-task LIBERO benchmark.

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

Custom object-swap cases are not standard LIBERO benchmark tasks for this fixed environment. They are used here as the core probes for instruction following and compositional generalization beyond exact official benchmark tasks.

The cream-cheese drawer case should be read as a positive OOD-composition example when the video shows the policy picking the cream cheese and placing it in the drawer. Cream cheese is an official LIBERO object, but this drawer target combination is not one of the 130 official benchmark instructions.

## How to Read Results

| Field | Interpretation |
|---|---|
| `manual check=pass` | Human inspection confirms the current instruction was followed. |
| `manual check=fail` | Human inspection shows the current instruction was not followed. |
| `manual check=pending` | The video is included, but this case still needs manual labeling. |
