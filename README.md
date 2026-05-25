# LIBERO Generalization Rollouts

This repository documents a small instruction-generalization probe on LIBERO policies.

The current report focuses on one fixed LIBERO task:

```text
suite: libero_goal
task_id: 3
official instruction: open the top drawer and put the bowl inside
original benchmark behavior: bowl -> top drawer
```

The key finding is based on manual video inspection. In several object-swap rollouts, the policy places the `bowl` in the top drawer even though the custom instruction asks for a different object such as `plate`, `wine bottle`, or `cream cheese`.

## Reports

- [Top drawer instruction generalization report](reports/top_drawer/index.html)

## Repository Layout

```text
reports/
  top_drawer/
    index.html
    videos/
    data/results.json
docs/
  methodology.md
```

The `reports/top_drawer/` directory is self-contained. It can be served through GitHub Pages or opened from a local static file server.

## Notes

- The report emphasizes manual video checks rather than automatic benchmark success.
- Object-swap and relation-swap instructions are OOD probes, not standard LIBERO benchmark tasks.
