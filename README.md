# 生成AI利用ガイドライン チェックリスト

![Status: WIP](https://img.shields.io/badge/status-WIP-yellow)
![License: MIT](https://img.shields.io/badge/license-MIT-blue)
![Built with mdBook](https://img.shields.io/badge/built_with-mdBook-blue)

組織が「生成AI利用ガイドライン」を策定・導入する際に、ガイドラインに必要な項目が網羅されているかを確認するための**メタチェックリスト**です。

## 想定読者

- 専門のIT部門や技術者がいない**小規模組織**の担当者
- 自組織の生成AI利用ガイドラインを新規に作成、または既存ガイドラインの抜け漏れを点検したい方

## チェックリストの構成

NIST AI RMF（AI Risk Management Framework）の構造を軸に、10カテゴリ・約180項目で構成しています。

| # | カテゴリ | 概要 |
|---|---------|------|
| 1 | ガバナンス体制 (GOVERN) | 組織体制・責任、ポリシー、教育、監査 |
| 2 | リスクの特定と評価 (MAP) | ユースケース定義、リスク分類、サードパーティ |
| 3 | 入力データの管理 | 入力禁止情報、データ分類、個人情報保護 |
| 4 | 出力の管理と利用 | 検証義務、著作権・知的財産、品質管理 |
| 5 | 信頼性の確保 | 正確性、安全性、セキュリティ、透明性、公平性 |
| 6 | 具体的な禁止事項 | 絶対的禁止、業務上の制限 |
| 7 | インシデント対応 | 報告体制、対応プロセス、記録と改善 |
| 8 | 運用管理 | ツール管理、アクセス管理、コスト、継続改善 |
| 9 | 特定用途・業界固有 | コード生成、文書作成、顧客対応、業界規制 |
| 10 | 文書としての完成度 | 構成・可読性、実効性、管理情報 |

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

[mdbook](https://rust-lang.github.io/mdBook/) でHTML版を生成できます。

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
├── book.toml                              # mdbook 設定
├── src/
│   ├── SUMMARY.md                         # 目次
│   ├── introduction.md                    # チェックリストについて・凡例
│   ├── ch01-governance.md                 # 1. ガバナンス体制
│   ├── ch02-risk-mapping.md               # 2. リスクの特定と評価
│   ├── ch03-input-data.md                 # 3. 入力データの管理
│   ├── ch04-output-management.md          # 4. 出力の管理と利用
│   ├── ch05-trustworthiness.md            # 5. 信頼性の確保
│   ├── ch06-prohibitions.md               # 6. 具体的な禁止事項
│   ├── ch07-incident-response.md          # 7. インシデント対応
│   ├── ch08-operations.md                 # 8. 運用管理
│   ├── ch09-domain-specific.md            # 9. 特定用途・業界固有
│   ├── ch10-document-quality.md           # 10. 文書としての完成度
│   ├── tips.md                            # 活用のヒント
│   ├── references.md                      # 参考ガイドライン一覧
│   └── changelog.md                       # 更新履歴
├── generative_ai_guideline_checklist_1.md # チェックリスト（単一ファイル版）
└── references/                            # 参照元ガイドライン文書（PDF等）
```

## ライセンス

[MIT License](LICENSE)
