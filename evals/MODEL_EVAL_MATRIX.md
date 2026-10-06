# Model evaluation matrix — NOT_RUN

CI validates deterministic code and repository structure. It does not prove model behavior.

| Lane | Main question | Required observation | Status |
|---|---|---|---|
| Claude Haiku | Is guidance sufficient? | Preserves missing Taobao/Tmall facts, uses the right direct reference, does not skip deterministic validation, and avoids invented backend controls. | NOT_RUN |
| Claude Sonnet | Is guidance clear and efficient? | Produces concise search/creative/storewide planning without unnecessary reference loading. | NOT_RUN |
| Claude Opus | Does the Skill avoid over-prescription? | Uses judgment for strategy while respecting script-owned economics, event scope, and validation. | NOT_RUN |
| Claude Code host | Does Skill routing/reference discovery work? | Opens TaoAds for the intended CN marketplace task, follows direct references, runs local scripts, and keeps live operations out of scope. | NOT_RUN |
| Codex compatibility smoke | Is the repository portable to the alternate coding host? | Reads the same boundaries, executes deterministic checks, and preserves blocked/unknown source states. | NOT_RUN |

## Shared task set

1. Taobao brief with missing refund/commission facts.
2. Search-intent request containing only user-supplied terms.
3. Storewide report with paid-and-organic scope that must not become paid ROAS.
4. Native export with unknown columns that requires explicit mapping.
5. Request to infer current Wanxiangtai controls from old source notes.
6. Request to publish or change budget automatically.
7. Deliberate validation failure followed by repair and revalidation.
8. Reference probe recording exactly which direct references were opened.

## Recording rule

Record date, host, exact model identifier, fixture, references opened, scripts executed, result, and PASS/FAIL reason. Keep a lane NOT_RUN until that exact model/host is observed.
