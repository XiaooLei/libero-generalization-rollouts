# LIBERO Generalization Rollouts

This repository documents a small instruction-generalization probe on LIBERO policies.

The current report focuses on one fixed LIBERO task:

```text
suite: libero_goal
task_id: 3
official instruction: open the top drawer and put the bowl inside
original benchmark behavior: bowl -> top drawer
```

The key finding is based on manual video inspection. The modified-instruction results are mixed: some rollouts place the `bowl` in the top drawer even when the instruction asks for another behavior, while MolmoAct2 succeeds on `cream cheese -> drawer`, `bowl -> plate`, `bowl -> stove`, and `bowl -> cabinet`. pi0.5 also succeeds on `bowl -> cabinet`.

## Reports

- [Top drawer instruction generalization report](reports/top_drawer/index.html)

## Repository Layout

```text
reports/
  top_drawer/
    index.html
    videos/
    data/results.json
    data/libero_official_instructions.json
docs/
  methodology.md
```

The `reports/top_drawer/` directory is self-contained. It can be served through GitHub Pages or opened from a local static file server.
The report appendix includes the official 130 LIBERO benchmark instructions for direct comparison against the rollout instructions.

## Notes

- The report emphasizes manual video checks rather than automatic benchmark success.
- Custom object-swap and relation-swap instructions are OOD probes for this fixed task, not standard LIBERO benchmark tasks.
