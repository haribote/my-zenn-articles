---
name: new-article
description: frontmatter 付きで新規 Zenn 記事を雛形作成する。この Zenn リポジトリで新しい記事・投稿を書き始めたいときに使う。
disable-model-invocation: true
---

# 新規 Zenn 記事を作成する

`$ARGUMENTS` にはタイトルや topics が含まれる場合がある。それらを frontmatter の入力に使う。

## 手順

1. `npm run new:article` を実行して記事ファイルを生成する。`articles/<random-slug>.md` が有効な（永続的な）slug で作成されるので、出力されたパスを控える。
   - ユーザーが明示的に slug を指定した場合のみ手書きする。slug は `a-z0-9-_` の 12〜50 文字で、公開後は変更できない。
2. 生成されたファイルの frontmatter を編集する:
   - `title`: `$ARGUMENTS` から取得。なければユーザーに尋ねる。
   - `emoji`: 内容に合う絵文字を1つ選ぶ。
   - `type`: 技術記事は `"tech"`、意見・アイデア記事は `"idea"`。デフォルトは `"tech"`。
   - `topics`: `$ARGUMENTS` やトピックから小文字タグを最大5件。
   - `published`: ユーザーが公開を指示するまで `false` のままにする。
3. 本文はユーザーが書くために空けておく。依頼があればアウトラインを下書きする。
4. ローカル確認用に `npm run preview`、文章チェック用に `npm run lint` を案内する。

ユーザーが明示的に依頼しない限り `published: true` にしない。
