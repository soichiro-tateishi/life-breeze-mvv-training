# Life Breeze MVV研修プロジェクト

Life Breezeのインターン生向けMVV研修を設計・管理するプロジェクトです。

---

## ディレクトリ構成

```
life-breeze-mvv-training/
├── README.md                  ← このファイル（全体案内）
├── docs/
│   ├── project_overview.md    ← プロジェクト設計書
│   ├── source_of_truth.md     ← MVV正本定義書（公式サイト準拠）
│   └── site_vs_pdf_diff.md    ← 公式サイト vs PDF 差分分析
├── slides/
│   └── mvv_training_intern_v0_1.md  ← スライド原稿（メイン成果物）
├── facilitation/
│   ├── facilitator_notes_intern.md  ← 話し手メモ
│   └── workshop_guide_intern.md     ← ワーク進行案
├── prompts/
│   ├── genspark_prompt_intern.md    ← Genspark用統合プロンプト
│   └── claude_prompt_slidewriting.md ← Claude用スライド執筆プロンプト
├── reviews/
│   └── review_log.md               ← レビュー記録
└── archive/
    └── original_pdf_notes.md        ← 元PDF内容メモ
```

---

## クイックスタート

### 1. 現在の状態を確認する
- `slides/mvv_training_intern_v0_1.md` — スライド原稿（18枚・60分・日英併記）
- `docs/source_of_truth.md` — MVVの正本（修正時はここを参照）

### 2. スライドを修正する
1. `slides/mvv_training_intern_v0_1.md` を編集
2. MVV表記は `docs/source_of_truth.md` と完全一致させる
3. コミットメッセージ: `[slide] 変更内容`

### 3. Gensparkでスライド生成する
1. `prompts/genspark_prompt_intern.md` の内容をGensparkに投入
2. 出力結果を確認
3. 差分を `reviews/review_log.md` に記録
4. 必要な修正をMarkdown原稿に反映

### 4. 研修を実施する
1. `facilitation/facilitator_notes_intern.md` を事前に確認
2. `facilitation/workshop_guide_intern.md` でワーク進行を確認

---

## MVV正本ルール

> **このプロジェクトでは、Life Breeze公式サイト日本語版を最新の正本として扱います。**
> PDFや過去資料との齟齬がある場合、`docs/source_of_truth.md` が優先されます。

| 項目 | 正本 |
|------|------|
| Mission | 笑顔と可能性がめぐる未来をつくる。 |
| Vision | 誰もが、自分の時間を力に変え、前へ進める世界をつくる。 |
| Values | 5つ（現場 / 好奇心 / 笑顔 / つなぐ / 利他） |

---

## GitHub運用ルール

### ブランチ運用
| ブランチ | 用途 | 例 |
|---------|------|-----|
| `main` | 承認済み原稿 | — |
| `draft/*` | 作業中の変更 | `draft/v0.2-values-update` |
| `review/*` | レビュー中 | `review/v0.2` |

### ファイル命名ルール
```
スライド:  mvv_training_{audience}_v{major}_{minor}.md
ファシリ:  facilitator_notes_{audience}.md
プロンプト: genspark_prompt_{audience}.md
```
- `{audience}`: `intern` / `manager`（将来の分岐対応）

### コミットメッセージ
```
[type] 変更内容の要約

type: slide / facilitation / docs / prompt / review / fix
```
例:
- `[slide] Value 3の説明文を公式サイト準拠に修正`
- `[facilitation] Workshop 02のケース問題を追加`
- `[docs] source_of_truthにValues説明を追記`

### バージョン管理
| バージョン | 意味 |
|-----------|------|
| v0.x | ドラフト（Claude Code生成） |
| v1.x | Genspark投入後の確定版 |
| v2.x | 実施後フィードバック反映版 |

### Issueの切り方
- タイトル: `[対象] 変更内容`
- 例: `[slides] Value 5の説明追加`
- ラベル: `slide` / `facilitation` / `prompt` / `docs` / `review`

### Pull Requestの粒度
- 1つのスライド修正 = 1 PR
- 複数スライドにまたがる構造変更 = 1 PR
- docs/運用ルール変更 = 1 PR

### Genspark出力後の差分反映フロー
1. Gensparkでスライド生成
2. 出力結果を確認し、差分をメモ
3. `reviews/review_log.md` に記録
4. 必要な修正をMarkdown原稿に反映
5. PRで変更を記録・承認

---

## 将来の拡張

| 拡張 | 対応方法 |
|------|---------|
| 英語版 | `slides/mvv_training_intern_en_v1_0.md` を追加 |
| Manager版 | `slides/mvv_training_manager_v1_0.md` を追加 |
| ワーク追加 | `facilitation/workshop_guide_{audience}.md` を更新 |

---

## 次にClaude Codeに投げるべきプロンプト3本

### プロンプト1: レビュー依頼
```
slides/mvv_training_intern_v0_1.md をレビューしてください。
チェック項目:
- MVV表記がsource_of_truth.mdと完全一致しているか
- 18枚・60分の構成に無理がないか
- インターンにとってわかりにくい表現がないか
- 日英併記が正しいか
結果をreviews/review_log.mdに記録してください。
```

### プロンプト2: Gensparkプロンプトの更新
```
slides/mvv_training_intern_v0_1.md の最新内容を反映して、
prompts/genspark_prompt_intern.md を更新してください。
スライド原稿の変更点をすべてGensparkプロンプトに反映してください。
```

### プロンプト3: Manager版の分岐作成
```
slides/mvv_training_intern_v0_1.md をベースに、
manager版のスライド原稿を作成してください。
- ファイル名: slides/mvv_training_manager_v0_1.md
- 追加内容: 出向前提の立ち位置、中長期戦略、KPI、成功の定義
- Values: 正本の5つをベースに、PDFの実務的要素を補足
- archive/original_pdf_notes.md を参照
```
