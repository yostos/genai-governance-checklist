# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.1] - 2026-02-14

### Changed
- サンプルガイドライン（guideline-sample.md）を改善
  - 個人情報の削除要求対応について追記（5.6.C）
  - 目次セクションを明示（7.1.A）
  - 行政委託事業への生成AI利用禁止規定を追記
- README.md および docs/guideline-sample/README.md
  - 生成AIサービス・プラン選定時の確認ポイントを整理
  - IT Governance の状態に関する注意書きを追記
  - FAQ 作成の推奨について記載
  - 日本語表現の統一性を改善
- todo.md
  - Phase 1〜3 の完了状況を更新
  - 対応項目数を整理

## [1.0.0-rc.1] - 2026-01-29

リリース候補版（Release Candidate）。フィードバックを募集しています。

### Added

- 全7章・120項目のチェックリスト
  - ch01: ガバナンス体制 (GOVERN)
  - ch02: リスクの特定と評価 (MAP)
  - ch03: 入力データの管理
  - ch04: 出力の管理と利用
  - ch05: 信頼性の確保 (Trustworthiness)
  - ch06: インシデント対応
  - ch07: ガイドラインとしての完成度
- 3段階の準拠レベル（Required / Recommended / Option）
- 各項目に「説明」と「定義例」を付与
- 用語集（glossary.md）- 22用語収録
- 準拠レベルの判断根拠（appendix-decisions.md）
- 参考ガイドライン一覧（references.md）
- Excel版セルフチェックシート

### Referenced Standards

- NIST AI RMF 1.0 (AI 100-1)
- NIST AI 600-1 Generative AI Profile
- AI推進法（令和7年法律第53号）
- 経済産業省・総務省「AI事業者ガイドライン」
- EU AI Act
- 日本ディープラーニング協会「生成AIの利用ガイドライン」
- IPA「テキスト生成AI導入・運用ガイドライン」

[Unreleased]: https://github.com/yostos/genai-governance-checklist/compare/v1.0.1...HEAD
[1.0.1]: https://github.com/yostos/genai-governance-checklist/compare/v1.0.0-rc.1...v1.0.1
[1.0.0-rc.1]: https://github.com/yostos/genai-governance-checklist/releases/tag/v1.0.0-rc.1
