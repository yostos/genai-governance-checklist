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
├── introduction.md          # 凡例（参照元・ガイドライン準拠レベル）
├── ch01-governance.md       # 1. ガバナンス体制 (GOVERN)
├── ch02-risk-mapping.md     # 2. リスクの特定と評価 (MAP)
├── ch03-input-data.md       # 3. 入力データの管理
├── ch04-output-management.md # 4. 出力の管理と利用
├── ch05-trustworthiness.md  # 5. 信頼性の確保 (Trustworthiness)
├── ch06-incident-response.md # 6. インシデント対応
├── ch07-document-quality.md # 7. ガイドラインとしての完成度
├── references.md            # 参考ガイドライン一覧
├── appendix-decisions.md    # ガイドライン準拠レベルの判断根拠（付録）
├── changelog.md             # 更新履歴
└── SUMMARY.md               # mdbook 目次
references/                  # 参照元ガイドライン文書（PDF/CSV/JSON）
references/INDEX.md          # 参照文献の一覧、ファイル対応表
docs/                        # プロジェクト管理文書
docs/roadmap.md              # 将来バージョンの対応予定
how-to-work.md               # アノテーション作業の詳細手順
```

## Checklist Item Format

各チェック項目は以下の形式で記述する:

```markdown
- X.X.Y. [Level] チェック項目テキスト [参照タグ]
  - **説明**: （1〜3文の日本語）
  - **定義例**: 「具体的な定義文」
```

- `X.X.Y`: セクション番号（例: 1.1.A, 2.3.C）
- `[Level]`: ガイドライン準拠レベル（下記参照）
- `[参照タグ]`: 参照元フレームワーク（末尾に配置）

## Enforcement Levels (ガイドライン準拠レベル)

| 表記            | 意味                                                                                 |
| --------------- | ------------------------------------------------------------------------------------ |
| **Required**    | ガイドラインに必ず記載すべき項目。欠落していると法令違反や重大リスクにつながる       |
| **Recommended** | ガイドラインに記載することを強く推奨する項目。除外する場合はその理由を説明できること |
| **Option**      | 記載があると望ましい項目。組織の規模や業種に応じて検討する                           |

ガイドライン準拠レベルの判断根拠は `src/appendix-decisions.md` に記録する。新たにレベルを決定した場合は必ず付録も更新すること。

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
- **改行ルール**: 日本語の文章は必ず80バイト以内に句読点（。、）などの区切りで改行すること。1行が80バイトを超えないようにする
- **アノテーション作業**: 説明・定義例の書き方の詳細ルールは `how-to-work.md` を参照
- **TODO.md の運用**: `TODO.md` は存在すれば読んで作業の参考にすること。ただし TODO.md の作成・削除のたびに CLAUDE.md を更新する必要はない

## Git Workflow

**CRITICAL: mainブランチへの直接コミットは禁止**

- mainブランチは保護されており、Pull Requestを経由した変更のみが許可される
- 修正作業を行う際は、必ず以下の手順を守ること:

### 修正作業の手順

1. **フィーチャーブランチの作成**
   ```bash
   git checkout -b feature/description-of-change
   # または
   git checkout -b fix/issue-description
   ```

2. **作業とコミット**
   - ブランチ上で修正を行う
   - 適切な粒度でコミットする
   - コミットメッセージは英語で、Conventional Commitsに従う

3. **プルリクエストの作成**
   ```bash
   git push -u origin feature/description-of-change
   gh pr create --title "タイトル" --body "説明"
   ```

4. **マージ**
   - レビュー不要の場合でもPRを経由してマージ
   - マージ後はローカルのmainを更新
   ```bash
   git checkout main
   git pull origin main
   git branch -d feature/description-of-change
   ```

### ブランチ命名規則

- `feature/`: 新機能追加
- `fix/`: バグ修正
- `docs/`: ドキュメント更新
- `chore/`: その他の雑務

**例外**: 緊急のホットフィックスでも、必ずブランチを切ってPRを作成すること。

## Current Work Status

**進捗**: 全7章完了（番号・準拠レベル・アノテーション）。
旧ch06（禁止事項）・旧ch07（運用管理）・旧ch08（特定用途）は全削除・番号繰り上げ済。
全120項目のチェックリストとして完成。

## Workflow for Annotation

各セクション（例: 5.2, 5.3）ごとに以下の手順で進める。**必ず1セクションずつ**進めること。

1. **準拠レベルの提案**: 全項目の番号・レベルを表形式で提案し、ユーザーの承認を得る
2. **ch05-\*.md の編集**: 番号・レベル・アノテーション（説明・定義例）を付与
3. **appendix-decisions.md の更新**: 判断根拠テーブルを追加
4. **textlint の実行**: 両ファイルをチェックし、エラーがあれば修正

## Key Decisions and Context

### Organization Context

- **対象組織**: 専門IT部門のない小規模組織、企業の経営相談を行う
- 経営相談で顧客の機密情報・個人情報を扱うため、ch03は全項目 Required
- 越境移転（3.3.D）は「海外サーバー処理前提で個人データ入力は原則禁止」

### Level Assignment Principles

- **SaaS制約**: SaaS型AI（ChatGPT、Claude等）の利用が前提。管理者向けログ機能が限定的なため、モニタリング・ログ保存系は Option（1.4.A, 4.4.B, 5.4.A）
- **整合性**: 同種の項目は章をまたいでもレベルを揃える（例: バイアス関連 → 2.2.D が Recommended なので 5.7 も Required なし）
- **実効性重視**: 小規模組織で実行不可能な形式的要件は Option に下げる

### Deleted Items

- **4.1.B**（確認すべき項目・観点）: 4.1.A と重複、削除
- **4.2.E**（学習データの著作権考慮）: 主要プロバイダ集約で無意味、削除
- **旧5.1.B**（情報源の確認・引用の推奨）: 4.1.A と重複、削除
- **ch06全体**（具体的な禁止事項・12項目）: ch01-05と重複、AI以前の一般行為規範、対象組織に無関係な項目のみで構成。章ごと削除
- **ch07全体**（運用管理・17項目）: ch01/05と重複、SaaS利用前提で不適、AI固有でない一般IT管理・コスト管理。章ごと削除
- **ch08全体**（特定用途・業界固有・18項目）: ch04/05が用途横断的にカバー済み、コード生成は対象組織に無関係、業界規制は1.2.Dに集約。章ごと削除

### User Preferences

- **簡潔第一**: アノテーションは短く実用的に
- **1セクションずつ**: まとめて提案せず、セクション単位で確認を取る
- **冗長項目の削除に積極的**: 重複・実務上無意味な項目は躊躇なく削除
