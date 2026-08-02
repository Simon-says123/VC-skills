---
name: preflight
description: Preflight health check for INT-VC-EVAL — VC skills collection (Cowork skills for venture workflows). Use before starting a session in this project, when the user runs /preflight, or asks whether the project is healthy/ready.
---

# Preflight — INT-VC-EVAL

Project root: `/Users/josh/IntelustryProjects/active/INT-VC-EVAL`

Run each check, record PASS / FAIL / WARN, then print the status table.

## Checks

**[1] Every skill has SKILL.md**
```bash
for d in /Users/josh/IntelustryProjects/active/INT-VC-EVAL/*/; do
  n=$(basename "$d")
  [ -f "$d/SKILL.md" ] && echo "PASS $n" || echo "FAIL $n missing SKILL.md"
done
```


## Status Table

After all checks, print a summary:

```
PREFLIGHT — INT-VC-EVAL
┌──────────────────────────┬────────┬──────────────────────────┐
│ Check                    │ Status │ Note                     │
├──────────────────────────┼────────┼──────────────────────────┤
│ ...                      │  ...   │ ...                      │
└──────────────────────────┴────────┴──────────────────────────┘
Overall: READY / DEGRADED / BLOCKED
```

- **READY** — all checks pass
- **DEGRADED** — non-critical failures (optional service down, missing dev deps)
- **BLOCKED** — a critical dependency is down (required env, API key, services needed to run)

If BLOCKED, list the exact fix commands before proceeding.

**BLOCKED when:** never — this is a content repo; failures are just missing skill files.
