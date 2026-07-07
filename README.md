# hearing-driven-writing

Claude Code 用スキル集。AIに「書いてもらう」のをやめて、「取材してもらう」ことにした。

## コンセプト

完璧主義で書けない書き手のために設計しています。AI が本文を書くのではなく、質問と選択肢で取材して、本人の言葉で書く流れを作ります。

AI に下書きを書かせると「AI臭い」文章になる。そうではなく、AI を聞き手・整理役に使い、書き手本人の言葉を引き出す——それがこのスキル集の方針です。

## 構成

| ファイル | 役割 |
|----------|------|
| `skills/zenn-interview/SKILL.md` | 取材。書き手から課題・エラー・発見・選択理由を引き出し素材化する |
| `skills/zenn-write/SKILL.md` | Zenn 技術記事の執筆支援。frontmatter・構成・Zenn独自Markdown・公開フローまで |
| `skills/koetsu/SKILL.md` | 校閲。textlint-ja 準拠の観点で表記ゆれ・誤字・文法誤用を赤入れ形式で指摘する |
| `agents/editor.md` | 3層編集エージェント。構成（developmental）→ line編集 を担当し、校正は koetsu に委譲する |

## インストール

1. `skills/` 配下の各ディレクトリを、あなたの `.claude/skills/` にコピーする。
2. `agents/editor.md` を、あなたの `.claude/agents/` にコピーする。

```
cp -r skills/* ~/.claude/skills/
cp agents/editor.md ~/.claude/agents/
```

Claude Code のプロジェクトごとに配置する場合は、プロジェクトルートの `.claude/skills/` および `.claude/agents/` に配置します。

## 使い方の流れ

```
/zenn-interview   # 取材して素材を引き出す
  ↓
/zenn-write       # 素材を核に技術記事を書く
  ↓
/koetsu           # 表記・誤字・文法を校閲する
  ↓
editor エージェント  # 構成・熱量・流れを編集診断する（必要に応じて）
```

## ライセンス

MIT — 詳細は [LICENSE](LICENSE) を参照してください。

校閲観点の出典については [NOTICE.md](NOTICE.md) を参照してください。

---

関連記事（Zenn / note）: 公開後にリンクを差し込む
