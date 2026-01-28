# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains a **Generative AI Utilization Guideline Checklist** (生成AI利用ガイドラインチェックリスト) — 組織が「生成AI利用ガイドライン」を作成・導入する際に、ガイドラインに必要な項目が網羅されているかを確認するためのメタチェックリストである。

- **目的**: ガイドライン文書そのものの網羅性・完成度をチェックする（ガイドラインのためのチェックリスト）
- **基準の中心**: 米国連邦政府の基準（NIST AI RMF等）を中心に、必要とされる項目を体系的にまとめている
- **対象ユーザー**: 専門のIT部門や技術者がいない小規模組織を主に想定
- **言語**: 日本語

スタンドアロンの参照文書であり、ソフトウェアプロジェクトではない。

## Repository Structure

mdbook プロジェクトとして構成されている。Rust（mdbook）は mise で管理。

```
src/
├── introduction.md          # 凡例（参照元・強制力レベル）
├── ch01-governance.md       # 1. ガバナンス体制 (GOVERN)
├── ch02-risk-mapping.md     # 2. リスクの特定と評価 (MAP)
├── ch03-input-data.md       # 3. 入力データの管理
├── ch04-output-management.md # 4. 出力の管理と利用
├── ch05-trustworthiness.md  # 5. 信頼性の確保 (Trustworthiness)
├── ch06-prohibitions.md     # 6. 具体的な禁止事項
├── ch07-incident-response.md # 7. インシデント対応
├── ch08-operations.md       # 8. 運用管理
├── ch09-domain-specific.md  # 9. 特定用途・業界固有の考慮事項
├── ch10-document-quality.md # 10. 文書としての完成度
├── tips.md                  # チェックリスト活用のヒント
├── references.md            # 参考ガイドライン一覧
├── appendix-decisions.md    # 強制力レベルの判断根拠（付録）
├── changelog.md             # 更新履歴
└── SUMMARY.md               # mdbook 目次
references/                  # 参照元ガイドライン文書（PDF/CSV/JSON）
references/INDEX.md          # 参照文献の一覧、ファイル対応表
how-to-work.md               # アノテーション作業の詳細手順
todo.md                      # 作業進捗管理
```

## Checklist Item Format

各チェック項目は以下の形式で記述する:

```markdown
- X.X.Y. [Level] チェック項目テキスト [参照タグ]
  - **説明**: （1〜3文の日本語）
  - **定義例**: 「具体的な定義文」
```

- `X.X.Y`: セクション番号（例: 1.1.A, 2.3.C）
- `[Level]`: 強制力レベル（下記参照）
- `[参照タグ]`: 参照元フレームワーク（末尾に配置）

## Enforcement Levels (強制力レベル)

| 表記 | 意味 |
| ---- | ---- |
| **Required** | ガイドラインに必ず記載すべき項目。欠落していると法令違反や重大リスクにつながる |
| **Recommended** | ガイドラインに記載することを強く推奨する項目。除外する場合はその理由を説明できること |
| **Option** | 記載があると望ましい項目。組織の規模や業種に応じて検討する |

強制力レベルの判断根拠は `src/appendix-decisions.md` に記録する。新たにレベルを決定した場合は必ず付録も更新すること。

## Reference Framework Tags

項目の末尾に参照元を以下の略称で付与する: `[NIST]`, `[NIST-GAI]`, `[METI]`, `[JDLA]`, `[IPA]`, `[FUJITSU]`, `[EU-AIA]`

**中心となる米国連邦政府基準:**
- NIST AI RMF 1.0 (AI Risk Management Framework)
- NIST AI-600-1 (Generative AI Profile)

**日本国内の基準:**
- 経済産業省・総務省 AI事業者ガイドライン (METI)
- 日本ディープラーニング協会 生成AI利用ガイドライン (JDLA)
- IPA テキスト生成AI導入ガイドライン (IPA)
- 文化庁 AIと著作権に関するガイドライン

**その他の国際基準:**
- EU AI Act (EU-AIA)
- ISO/IEC 42001:2023
- OECD AI Principles

## Working with This Document

- The document is written entirely in Japanese
- When editing, preserve the checklist item format (`X.X.Y. [Level] text [tags]`)
- Maintain the reference framework tags on each item
- Keep the bibliography section up to date when adding new reference sources
- **改行ルール**: 日本語の文章は必ず120バイト以内に句読点（。、）などの区切りで改行すること。1行が120バイトを超えないようにする
- **アノテーション作業**: 説明・定義例の書き方の詳細ルールは `how-to-work.md` を参照
