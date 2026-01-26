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

- `generative_ai_guideline_checklist_1.md` — チェックリスト本体（130+チェック項目、10カテゴリ）
- `references/` — 参照元ガイドライン文書（PDF/CSV/JSON）。詳細は `references/INDEX.md` を参照
- `references/INDEX.md` — 参照文献の一覧、ファイル対応表、未取得文書のURL

## Document Architecture

The checklist follows the NIST AI RMF structure (GOVERN, MAP, MEASURE, MANAGE) and is organized into these sections:

1. **GOVERN** — Governance, organizational structure, policies, training, monitoring
2. **MAP** — Risk identification, use case classification, third-party vendor evaluation
3. **Input Data Management** — Prohibited information types, data classification, personal data protection
4. **Output Management** — Validation, copyright/IP, quality control
5. **Trustworthiness** — Accuracy, safety, security, transparency, privacy, fairness
6. **Specific Prohibitions** — Absolute and business-context restrictions
7. **Incident Response** — Reporting, response processes, documentation
8. **Operational Management** — Tool management, access control, cost, continuous improvement
9. **Domain-Specific** — Code generation, documents, data analysis, customer service, industry regulations
10. **Document Completeness** — Structure quality and implementation feasibility

## Checklist Status Indicators

Each item uses this status system:
- ☐ Unchecked/Unknown
- ✓ Implemented
- △ Partially Implemented
- × Not Implemented
- N/A Not Applicable

## Reference Framework Tags

Items are tagged with source frameworks: `NIST`, `METI`, `JDLA`, `IPA`, `FUJITSU`, `EU-AIA`. These indicate alignment with:

**中心となる米国連邦政府基準:**
- NIST AI RMF 1.0 (AI Risk Management Framework)
- NIST AI-600-1 (Generative AI Profile)

**その他の国際基準:**
- EU AI Act
- ISO/IEC 42001:2023
- OECD AI Principles

**日本国内の基準:**
- 経済産業省・総務省 AI事業者ガイドライン (METI)
- 日本ディープラーニング協会 生成AI利用ガイドライン (JDLA)
- IPA テキスト生成AI導入ガイドライン (IPA)
- 文化庁 AIと著作権に関するガイドライン

## Working with This Document

- The document is written entirely in Japanese
- When editing, preserve the checklist formatting and section numbering
- Maintain the reference framework tags on each item
- Keep the bibliography section up to date when adding new reference sources
- **改行ルール**: 日本語の文章は必ず120バイト以内に句読点（。、）などの区切りで改行すること。1行が120バイトを超えないようにする
