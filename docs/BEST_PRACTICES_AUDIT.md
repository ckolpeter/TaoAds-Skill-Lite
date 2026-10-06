# Best-practices retrofit audit — 2026-10-06

Scope: TaoAds Skill Lite only. This is a repository/behavior-design audit, not Alibaba certification, live account verification, or a model-quality claim.

| Check | Result | Evidence |
|---|---|---|
| SKILL.md below 500 lines | PASS | Enforced by `scripts/release_gate.py`. |
| Runtime references are one hop from SKILL.md | PASS | Both reference files are directly listed; nested reference directories fail release. |
| Long references have a content list | PASS (guarded) | `data-contract.md` has a Contents section; future references over 100 lines without one fail. |
| Degrees of freedom explicit | PASS | Strategy = high, planning shape = medium, deterministic calculations/validation = low. |
| Ordered checklist | PASS | SKILL.md contains the order-sensitive checklist and return-on-failure rule. |
| Self-correction loop | PASS | Draft → validate → repair → revalidate; validator weakening is forbidden. |
| Dependencies explicit | PASS | Python 3.10+ standard library only; no third-party runtime dependency. |
| Cross-model evaluation | NOT_RUN | Required lanes are defined in `evals/MODEL_EVAL_MATRIX.md`; real host/model runs are still pending. |

## Important boundary

Blocked or failed source verification remains blocked/failed. Structural hardening must never convert an inaccessible official page into a verified platform capability. CI PASS does not imply live feature availability, attribution correctness, or performance.
