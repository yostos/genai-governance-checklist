# Checklist Annotation Workflow Guide

## Objective

Add **説明** (explanation) and **定義例** (definition example) as child nodes to each checklist item in `generative_ai_guideline_checklist_1.md`.

Target audience of the checklist: staff at **small organizations without dedicated IT departments** creating their own generative AI usage guidelines. The annotations must be immediately understandable and directly reusable in their own guidelines.

---

## Output Format

```markdown
- [ ] Checklist item text [NIST: GOVERN X.X] [METI]
  - **説明**: (1-3 sentences in Japanese)
  - **定義例**: 「Concrete wording in Japanese」
```

### Writing 説明 (Explanation)

Three-part structure (sentence 3 only when relevant):

1. **What the item requires** -- stated concisely
2. **What happens without it** -- concrete risk or consequence (NEVER omit this)
3. **Anti-pattern warning** -- common pitfall stated diplomatically (e.g., appointing a nominal leader who delegates everything and claims ignorance is equivalent to having no leader)

Rules:
- Do NOT repeat source references in the text. The tags `[NIST: GOVERN 2.3]` `[METI]` on the checklist item already serve that purpose.
- Write catchy, readable Japanese. Not too formal, not too casual.
- Metaphors or aphorisms are welcome when effective, but not required on every item.

### Writing 定義例 (Definition Example)

- Write **exactly one** example (not multiple).
- Target a small organization that can adopt it as-is.
- Must clearly include **who** does **what** and **how**.

---

## Investigation Procedure

For each checklist item:

### Step 1: Identify Source Tags

Read the suffix tags like `[NIST: GOVERN 2.1]` `[METI]` and determine which source documents to consult.

### Step 2: Read Source Documents

Read the corresponding PDFs in `references/` to find the original text. See `references/INDEX.md` for the full mapping.

Key tag-to-file mapping:

| Tag | File | Notes |
|-----|------|-------|
| NIST: GOVERN/MAP/MEASURE/MANAGE | `NIST_AI_RMF_1.0.pdf` | Subcategory definition (one-liner) |
| NIST (detailed actions) | `NIST_AI_600-1_GenAI_Profile.pdf` | Suggested Actions with IDs like GV-X.X-XXX |
| METI | `METI_AI_Guidelines_v1.1.pdf` | Japanese. Government AI guidelines |
| IPA | `IPA_TextGen_AI_Guideline.pdf` | Japanese. Practical deployment guide |
| JDLA | Not downloaded locally | Requires form-based download. Supplement via web search |
| FUJITSU | `FUJITSU_GenAI_Guidelines.pdf` | Corporate best practice example |
| EU-AIA | `EU_AI_Act_Full.pdf` | English. Risk-based approach |

**Important**: NIST AI RMF 1.0 contains only one-line subcategory definitions. The concrete Suggested Actions are in `NIST_AI_600-1_GenAI_Profile.pdf` (with action IDs like GV-2.1-001). Always consult both.

### Step 3: Draft and Insert

Draft 説明 and 定義例 based on investigation results, then insert into the markdown file as child nodes under the checklist item.

---

## Rules Established Through User Feedback

These were refined through actual review iterations:

1. **No source repetition in text**: Never write things like "NIST AI RMF requires... (GOVERN 2.3)" inside 説明. The prefix tags already convey the source.
2. **Keep it concise**: Short, impactful phrasing over lengthy explanation.
3. **One definition example only**: Do not list multiple variants (large/mid/small org). One example targeting small organizations.
4. **Never drop the risk statement**: "What happens without it" must always be present. Omitting it halves the persuasiveness.
5. **State anti-patterns explicitly**: For items prone to becoming ceremonial, describe the NG pattern in diplomatic language (e.g., "a nominal responsible person who delegates everything while remaining uninvolved is equivalent to having no responsible person").

---

## Approved Examples (2 items finalized with user)

```markdown
- [ ] 生成AI利用に関する最終責任者（経営層）が明確に定められている [NIST: GOVERN 2.3] [METI]
  - **説明**: AIで問題が起きたとき誰が最終判断を下すのか、即答できる状態をつくる。責任者が不明確だと、インシデント発生時に判断が宙に浮き、対応の遅れが法的・社会的リスクを組織全体に波及させる。また、名目上の責任者を置くだけでも不十分——実務を担当者に任せきりにし、責任者自身がリスクや運用実態を把握していない体制は「責任者不在」と同義である。
  - **定義例**: 「団体理事長をAI利用の最終責任者とし、利用方針の承認・リスク受容の判断・重大インシデント時の意思決定を自ら行う。定期的に運用状況の報告を受け、方針の妥当性を確認する」
- [ ] AI利用に関する担当部門・担当者が指定されている [NIST: GOVERN 2.1] [JDLA]
  - **説明**: 最終責任者の下で、日常のAI利用を実務面で管理する部門・担当者を明確にする。指定がないと、利用上の疑問やトラブルの相談先が不在となり、現場が自己判断で使い続ける"野良AI"状態を招く。
  - **定義例**: 「総務部をAI利用の管理部門とし、担当者○○がツール選定・利用ルールの周知・問い合わせ対応・インシデント一次対応を担う」
```

---

## Progress

- **Done**: Sections 1–4 complete (75 items)
  - 1. ガバナンス体制 (GOVERN): 21 items
  - 2. リスクの特定と評価 (MAP): 21 items
  - 3. 入力データの管理: 16 items
  - 4. 出力の管理と利用: 17 items
- **Next**: Section 5.1 `正確性・信頼性` (5 items)
- **Total scope**: 180 checklist items across ~40 subsections
