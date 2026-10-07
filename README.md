# TaoAds Skill Lite v1.1.0 — Public Preview

[繁體中文](docs/i18n/README.zh-TW.md) · [简体中文](docs/i18n/README.zh-CN.md) · [English](docs/i18n/README.en.md) · [日本語](docs/i18n/README.ja.md) · [한국어](docs/i18n/README.ko.md)

[AI Ads Academy／AI 廣告學院](https://www.ai-ads.academy)

淘寶／天貓搜尋意圖、素材與全店企劃，優惠退款與損益檢查。中國大陸 CN／CNY 專用；不是平台官方產品。

## 基礎功能

依提供資料做準備度、代表性訂單損益、等額試投會計情境、平台專用工作清單，以及描述性報表分析。
`china_context` 明確記錄商家端、生命週期、優惠退款成本确认；素材權利、素材供給與直播準備會影響候選狀態。

| 本地模式 | 規劃流程（不是 API 枚舉） |
|---|---|
| `search_intent` | 確認淘寶或天貓商家端實際可用功能 → 只整理使用者提供的搜尋詞 → 按需求與商品證據組織素材 → 不虛構搜尋量、競價或否定字控制 |
| `audience_creative` | 從提供的人群需求形成素材假設 → 核對商品主張與素材權利 → 一次只改一個素材變因 → 以相同歸因口徑評估 |
| `storewide` | 核對全店與商品成交邊界 → 整理到手價與佣金退款口徑 → 建立等額試投會計情境 → 不把混合營收當純付費 ROAS |

## 快速開始

Python 3.10+，僅標準函式庫，無需 pip、npm、Docker 或廣告憑證。在 Repo 根目錄執行：

```bash
python3 scripts/toolkit.py plan examples/brief.synthetic.json --out-dir output/demo-plan
python3 scripts/toolkit.py validate output/demo-plan/plan.json
python3 scripts/toolkit.py analyze examples/report.csv --meta examples/report.meta.json --out-dir output/demo-report
python3 -m unittest discover -s tests -v
python3 scripts/release_gate.py
```

輸出 JSON 可重播驗證，Markdown 供人閱讀。目錄存在時拒絕覆寫，重跑需換新的 output 子目錄。
CLI 不內建模型；由 Codex／Claude Code 讀取 SKILL.md 後可寫另一份解讀，不要改寫 deterministic JSON。

## 資料與邊界

複製 templates/brief.json，已知資料填入，未知保留 null。成本不能省略當零，優惠／退款已扣淨收入者不可重複扣成本。
JSON／CSV 均只支援本套件契約；CSV 須附 metadata，不自動猜平台原始匯出欄位。
完整欄位、事件定義、貨幣與公式見 [data contract](references/data-contract.md)。

PLAN_READY／ANALYSIS_READY 只代表本地結構完成；publish_authorized、external_reads、external_writes 永遠為 false。
沒有 API、登入、即時資料、網頁抓取、廣告發布、預算修改、平台審核或成效保證。模型端可能使用雲端；不要提供未去識別個資。
ROI／ROAS／毛 GMV／結算收入／利潤不可互換；全域資料不等於純付費或因果增量。

## 開發與核驗

[安裝](docs/INSTALLATION.md) · [接手指南](docs/HANDOFF.md) · [驗證說明](docs/TEST_REPORT.md) · [Best-practices audit](docs/BEST_PRACTICES_AUDIT.md) · [Model eval matrix](evals/MODEL_EVAL_MATRIX.md) · [官方來源狀態](references/official-sources.md)

五語為入門說明，不代表 CLI 全語系化、平台法規適用或桌面 Agent 自動選用已驗證。需要真人廣告判斷。
本地工作流刻意不凍結快速變動的後台產品選項；商家須核對帳號實際可用能力。

開源：Apache-2.0。共用基礎衍生自同作者 SpeAds；每包含完整獨立程式，不依賴其他 Repo 或網路。
