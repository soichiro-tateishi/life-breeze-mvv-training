# Claude用 スライド執筆プロンプト集

> **使い方**: スライド原稿の修正・追加時にClaude Chatに投げるプロンプトテンプレート。
> **正本参照**: 修正時は必ず `docs/source_of_truth.md` の内容と整合性を確認すること。

---

## プロンプト1: スライド1枚の修正

```
あなたはLife Breezeのインターン向けMVV研修のスライドライターです。

以下の正本MVVに準拠して、指定されたスライドの原稿を修正してください。

【正本MVV】
Mission: 笑顔と可能性がめぐる未来をつくる。 / Create a future where smiles and possibilities grow.
Vision: 誰もが、自分の時間を力に変え、前へ進める世界をつくる。 / Build a world where people turn time into strength and move forward.
Values:
1. まず現場に立つ。 / Start from the ground.
2. 知ろうとし続ける。 / Stay curious. Stay humble.
3. 笑顔につながる価値をつくる。 / Create value that leads to smiles.
4. 受けた価値を、次へつなぐ。 / Pay forward the value you receive.
5. 利他で考え、続く形にする。 / Think beyond yourself. Make it last.

【修正対象スライド】
（ここにスライド番号と現在の原稿を貼る）

【修正指示】
（ここに修正内容を記載）

出力形式: 修正後のスライド原稿をMarkdownで出力してください。日英併記でお願いします。
```

---

## プロンプト2: 新しいスライドの追加

```
あなたはLife Breezeのインターン向けMVV研修のスライドライターです。

以下の条件で新しいスライドの原稿を作成してください。

【正本MVV】
（上記と同じ）

【追加するスライドの条件】
- スライド番号: #XX（Slide YYとZZの間に追加）
- テーマ: （テーマを記載）
- 時間: X分
- 対象: インターン生（新規参加者）

【既存の前後スライドの内容】
前: （前のスライドの概要）
後: （後のスライドの概要）

出力形式: 既存スライドのフォーマットに合わせたMarkdownで出力してください。日英併記でお願いします。
```

---

## プロンプト3: ファシリテーターノートの追加

```
あなたはLife BreezeのMVV研修のファシリテーション設計者です。

以下のスライド原稿に対応するファシリテーターノートを作成してください。

【スライド原稿】
（ここにスライド原稿を貼る）

【出力に含めること】
- 話すポイント（3つ程度）
- 強調箇所（1つ）
- 注意事項（1つ）
- トーンの指定

出力形式: 既存のファシリテーターノート（facilitation/facilitator_notes_intern.md）と同じフォーマットで。
```

---

## プロンプト4: 英語版への変換

```
あなたはLife BreezeのMVV研修の翻訳者です。

以下の日本語スライド原稿を英語版に変換してください。

【翻訳ルール】
- MVV本体の英語表記は正本に準拠（勝手に意訳しない）
- 説明文は自然な英語に翻訳
- インターン向けのトーンを維持（フォーマルすぎない）
- フォーマットはMarkdownで、日本語版と同じ構造を維持

【正本MVV英語版】
Mission: Create a future where smiles and possibilities grow.
Vision: Build a world where people turn time into strength and move forward.
Values:
1. Start from the ground.
2. Stay curious. Stay humble.
3. Create value that leads to smiles.
4. Pay forward the value you receive.
5. Think beyond yourself. Make it last.

【翻訳対象スライド】
（ここにスライド原稿を貼る）
```
