# Official sources and verification limits

Snapshot: 2026-10-05. Sources describe product scope, not current account eligibility. No live lookups occur in the package.

## TAOADS-1 — 阿里媽媽萬相台入口

https://one.alimama.com/

Status: `blocked_403`. Portal fetch returned 403; current labels, bidding controls and feature availability are NOT verified.

## TAOADS-2 — 阿里開發者文件入口

https://developer.alibaba.com/docs/api.htm?apiId=70503

Status: `fetch_failed`. Page timed out. No API schema, permission or live enum is derived from it.

Mode names, checklists and planning rules are our local design, not copied official API contracts. Blocked/empty pages are not treated as verified. Obtain de-identified current backend samples before building importers or capability mappings.
