# skills

Claude Code 用のスキル集。nonbiri-bookstore が実際に使っている `.claude` から配布しています。

配布物はこの1リポジトリに集約し、`skills/<category>/<skill>/` で分類します。いまは `writing`（日本語ライティング）から始めています。

## コンセプト

AI に「書いてもらう」と、整ってはいるのに「自分の文章じゃない」ものが出てくる。原因は、AI が書き手を知らないまま一般論を整えているからです。

このスキル集は、その順番を変えます。**AI に本文を書いてもらうのではなく、取材してもらう。** 質問と選択肢で書き手の言葉を引き出し、それを核に書く。完璧主義で着手できない人ほど、効きます。

## クイックスタート

```bash
npx skills@latest add nonbiri-bookstore/skills
```

対話で使いたいスキルを選ぶと `.claude/` に入ります。

手動で入れる場合:

```bash
# スキル
cp -r skills/<category>/<skill> ~/.claude/skills/
# エージェント
cp .agents/editor.md ~/.claude/agents/
```

## 収録スキル

### writing — 日本語ライティング

| 名前 | 種別 | 起動 | 役割 |
|------|------|------|------|
| `zenn-interview` | skill | user | 取材。AI が本文を書かず、質問と選択肢で書き手の言葉を引き出す |
| `zenn-write` | skill | user / model | 技術記事の執筆。frontmatter・構成テンプレ・Zenn独自Markdown・公開フロー |
| `koetsu` | skill | user / model | 校閲。表記ゆれ・誤字・ら抜き・一文長などを赤入れ（textlint-ja 準拠） |
| `editor` | agent | subagent | 編集。構成・主題・熱量を診断する3層編集（developmental / line / copy） |

推奨フロー: `zenn-interview`（取材）→ `zenn-write`（下書き）→ `koetsu`（校閲）→ `editor`（編集）。

## ライセンス

MIT License. クレジットは [NOTICE.md](./NOTICE.md) を参照（校閲ルールは textlint-ja に基づく）。

---

関連記事:

- note（エッセイ）: https://note.com/benihistudio/n/ne7034862748e
- Zenn（技術）: 公開URL確定後に差し込みます
