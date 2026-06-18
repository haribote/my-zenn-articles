# CLAUDE.md

このファイルは、本リポジトリで作業する際の Claude Code (claude.ai/code) 向けガイドです。

`zenn-cli` で管理する [Zenn](https://zenn.dev) のコンテンツリポジトリ（記事と本）です。

## コマンド

- `npm run preview` — ローカルの Zenn プレビューサーバーを起動（http://localhost:8000）
- `npm run new:article` — `articles/` に新規記事を作成（ランダム slug、下書き frontmatter）
- `npm run new:book` — `books/` に新規の本を作成
- `npm run lint` — 全記事・本に textlint を実行
- `npm run lint:fix` — textlint を autofix 付きで実行

## コンテンツ規約

- 記事は `articles/<slug>.md` に置く。slug は `a-z0-9-_` の 12〜50 文字で、公開後は URL になるため変更不可 — 公開済み記事のファイル名はリネームしない。
- 本は `books/<book-slug>/` に置き、`config.yaml` と章ごとの `.md` ファイルで構成する。
- 記事の frontmatter:
  ```yaml
  ---
  title: ""          # 記事タイトル
  emoji: "😀"        # アイキャッチ絵文字1つ
  type: "tech"       # "tech"（技術記事）or "idea"（アイデア記事）
  topics: []         # タグ。最大5件、英数字小文字推奨（例: ["nextjs", "typescript"]）
  published: false   # true で公開
  ---
  ```
- 下書き中は `published: false` のままにし、公開準備ができたときだけ `true` にする。

## 執筆

- 記事本文は**日本語**で書く（技術用語・コード・識別子は英語のまま）。
- textlint（`preset-ja-technical-writing`）が日本語の文章をチェックする。公開前に警告を修正するか正当な理由を確認する。autofix 可能なものは `npm run lint:fix` で対応する。

## 公開ワークフロー

- 記事ごとにブランチを切り、PR を作成して `main` にマージする。`main` に変更が入ると Zenn–GitHub 連携で自動的に公開される。
