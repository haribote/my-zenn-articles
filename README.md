# my-zenn-articles

[Zenn](https://zenn.dev) の記事・本を `zenn-cli` で管理するリポジトリです。

* [📘 Zenn CLI の使い方](https://zenn.dev/zenn/articles/zenn-cli-guide)

## npm scripts

| コマンド | 説明 |
| --- | --- |
| `npm run preview` | ローカルプレビューサーバーを起動（http://localhost:8000） |
| `npm run new:article` | `articles/` に新規記事を作成 |
| `npm run new:book` | `books/` に新規の本を作成 |
| `npm run lint` | 記事・本に textlint を実行 |
| `npm run lint:fix` | textlint を autofix 付きで実行 |

文章の校正には [textlint](https://textlint.github.io/)（`preset-ja-technical-writing`）を使用します。設定は `.textlintrc.json` を参照してください。

## 公開ワークフロー

記事ごとにブランチを切り、PR を作成して `main` にマージします。`main` に変更が入ると Zenn–GitHub 連携で自動的に公開されます。

## Claude Code Skills

このリポジトリには [Claude Code](https://claude.com/claude-code) 用のスキルが含まれています。

| スキル | 説明 |
| --- | --- |
| `/new-article` | frontmatter 付きで新規 Zenn 記事を雛形作成する |

スキルの定義は `.claude/skills/` 配下にあります。また、`articles/`・`books/` 配下の `.md` を編集すると、`.claude/settings.json` の hook により textlint が自動実行されます。
