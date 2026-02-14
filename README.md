# 生成AI利用ガイドライン チェックリスト

![License: MIT](https://img.shields.io/badge/license-MIT-blue)
![Built with mdBook](https://img.shields.io/badge/built_with-mdBook-blue)
![textlint](https://github.com/yostos/genai-governance-checklist/actions/workflows/textlint.yml/badge.svg)
![Deploy](https://github.com/yostos/genai-governance-checklist/actions/workflows/deploy.yml/badge.svg)

📖 **[チェックリストを読む（GitHub Pages）](https://yostos.github.io/genai-governance-checklist/)**

組織が「生成AI利用ガイドライン」を策定・改訂する際に、必要な項目が網羅されているかを確認するための**メタチェックリスト**です。生成AIの利用ルールそのものではなく、ガイドラインの**過不足を点検する**ためのチェックリストです。

## 想定読者

- 専門のIT部門を持たない**中小規模の組織**で、生成AIの利用ガイドラインを策定・点検する担当者
- AIやリスク管理の専門知識がなくても、項目を順に確認できるよう各項目に説明と定義例を付している

## このチェックリストを使う利点

- 国際的な基準（NIST AI RMF等）に照らして、自組織のガイドラインの過不足を**客観的に把握**できる
- 準拠レベル（Required / Recommended / Option）により、限られたリソースの中で**何を優先すべきか**が判断できる
- ガイドラインの網羅性について社内外から説明を求められた際の**客観的な根拠**となる

## 対象範囲

ChatGPT・Claude・Gemini等の**SaaS型生成AIサービス**を業務で利用する場面を対象としています。自社でのAIモデル開発・訓練や、ソフトウェア開発におけるコード生成の用途は対象外です。

## チェックリストの構成

NIST AI RMF（AI Risk Management Framework）の4機能（GOVERN・MAP・MEASURE・MANAGE）に沿って構成しています。全7章・**120項目**です。

| 章 | タイトル | 概要 | 主な対応基準 |
|----|---------|------|-------------|
| 1 | ガバナンス体制 | 責任者・ポリシー・教育など組織の管理体制 | NIST GOVERN |
| 2 | リスクの特定と評価 | 利用目的の明確化とリスクアセスメント | NIST MAP |
| 3 | 入力データの管理 | 入力禁止情報・個人情報・機密情報の取り扱い | NIST-GAI, JDLA |
| 4 | 出力の管理と利用 | 出力の検証義務・著作権・利用範囲 | NIST MEASURE, NIST-GAI |
| 5 | 信頼性の確保 | 正確性・安全性・公平性・透明性などの品質特性 | NIST Trustworthiness |
| 6 | インシデント対応 | 報告体制と対応手順 | NIST MANAGE |
| 7 | ガイドラインとしての完成度 | 文書としての一般的な品質要件 | — |

### 準拠レベル

| 表記 | 意味 |
|------|------|
| **Required** | ガイドラインに必ず記載すべき項目。欠落していると法令違反や重大リスクにつながる |
| **Recommended** | 記載を強く推奨する項目。除外する場合はその理由を説明できること |
| **Option** | 記載があると望ましい項目。組織の規模や業種に応じて検討する |

## Excel版チェックリスト

セルフチェック用のExcelワークシートを用意しています。ドロップダウンで対応状況を記入でき、サマリーシートで対応率を自動集計します。

**ダウンロード**: [`excel/genai-governance-checklist.xlsx`](excel/genai-governance-checklist.xlsx)

## サンプルガイドライン

チェックリストの Required / Recommended 項目を満たすガイドラインのサンプル文書を用意しています。

📄 **[サンプルを見る](docs/guideline-sample/guideline-sample.md)** | **[HTML版](docs/guideline-sample/guideline-sample.html)**

- **想定組織**: 専門IT部門を持たない中規模組織（職員233名）
- **想定読者**: ITリテラシーが低い非エンジニアの職員
- **対応項目**: Required 74項目 + Recommended 19項目

サンプルは、IT Governance の基盤が十分でない組織が「まず最低限のルールを整備する」ことを優先した実用重視の内容です。理想的なガイドラインではなく、現実的な出発点として位置づけてください。詳細は [利用上の注意](docs/guideline-sample/README.md#利用上の注意) を参照してください。

## 参照フレームワーク

各項目には出典タグを付与しています。

| タグ | 文書名 |
|------|--------|
| `[NIST]` | NIST AI Risk Management Framework (AI RMF 1.0) |
| `[NIST-GAI]` | NIST AI RMF Generative AI Profile (NIST AI 600-1) |
| `[METI]` | 経済産業省・総務省「AI事業者ガイドライン」 |
| `[JDLA]` | 日本ディープラーニング協会「生成AIの利用ガイドライン」 |
| `[IPA]` | IPA「テキスト生成AI導入・運用ガイドライン」 |
| `[FUJITSU]` | 富士通「生成AI利活用ガイドライン」 |
| `[EU-AIA]` | EU AI Act (EU AI規制法) |

## ビルド方法

[mdBook](https://rust-lang.github.io/mdBook/) でHTML版を生成できます。

```bash
# mdbook のインストール（未導入の場合）
cargo install mdbook

# ビルド
mdbook build

# ローカルプレビュー
mdbook serve --open
```

生成されたHTMLは `book/` ディレクトリに出力されます。

## ファイル構成

```
├── book.toml                    # mdbook 設定
├── src/
│   ├── SUMMARY.md               # 目次
│   ├── introduction.md          # チェックリストについて・凡例
│   ├── ch01-governance.md       # 1. ガバナンス体制
│   ├── ch02-risk-mapping.md     # 2. リスクの特定と評価
│   ├── ch03-input-data.md       # 3. 入力データの管理
│   ├── ch04-output-management.md # 4. 出力の管理と利用
│   ├── ch05-trustworthiness.md  # 5. 信頼性の確保
│   ├── ch06-incident-response.md # 6. インシデント対応
│   ├── ch07-document-quality.md # 7. ガイドラインとしての完成度
│   ├── references.md            # 参考ガイドライン一覧
│   ├── appendix-decisions.md    # 準拠レベルの判断根拠
│   ├── glossary.md              # 用語集
│   └── changelog.md             # 更新履歴
├── docs/
│   └── guideline-sample/        # サンプルガイドライン
│       ├── guideline-sample.md  # 本文（Markdown）
│       ├── guideline-sample.html # 本文（HTML）
│       └── organization-profile.md # 想定組織プロファイル
├── excel/
│   └── genai-governance-checklist.xlsx  # セルフチェック用Excel
├── tools/
│   ├── generate_excel.py        # Excel生成スクリプト
│   └── docs/excel-spec.md       # Excel仕様書
└── references/                  # 参照元ガイドライン文書（PDF等）
```

## ライセンス

[MIT License](LICENSE)
