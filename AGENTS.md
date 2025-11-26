# Repository Guidelines

## プロジェクト構成と管理

- `articles/*.md`: Zenn 記事本体。各ファイル 1 テーマ。既存と同じ見出し粒度を維持し、YAML フロントマターを必ず付与。
- `books/`: 将来の Zenn 本用。章追加は CLI で生成し、手書きで階層を作らない。
- `images/`: 共有画像。例: `python-exam-certificate.jpg`。参照は `![alt](/images/...)` で絶対パスを推奨。
- `memo/`: Git 無視の下書き置き場。公開準備前のメモやスニペットはここに。
- ルート: `package.json`/`package-lock.json` は `zenn-cli` を固定。`README.md` はリポジトリ概要。

## セットアップ・ビルド・プレビュー

- 初回セットアップ: `npm install`
- 記事生成: `npx zenn new:article --slug leetcode-roman-to-integer --title "LeetCode: Roman to Integer"`
- 本生成: `npx zenn new:book --slug data-structures --title "Data Structures"`
- プレビュー: `npx zenn preview`（ドラフトと公開済みを確認）。`--open` で自動ブラウザ起動。
- テスト: 自動テストは未整備。`npm test` はプレースホルダーで失敗終了。

## 執筆スタイル

- フロントマター必須キー: `title`, `emoji`, `type`, `topics`, `published`。公開前は `published: false`。
- Markdown は明確な `##`/`###` 階層とフェンスコードを使用（例: ```python）。
- スラッグ/ファイル名: ASCII ケバブケースで内容が伝わるもの（例: `leetcode-roman-to-integer`）。途中変更は避ける。
- リンク・画像: リポジトリルートからの絶対パスを優先し、リンク切れや画像未表示がないか確認。

## テストと検証

- コミット前に `npx zenn preview` でレンダリング・リンク・フロントマターをチェック。
- 画像は 1MB 未満を目安に圧縮し、未使用ファイルは `images/` から整理。

## コミットと PR

- コミットは履歴に倣い、現在形・スコープ付きの短文を推奨（例: `docs(advent): draft planning document`, `feat(article): add roman-to-integer`）。
- PR には概要、関連 Issue、追加・更新した記事/章の一覧、レイアウト変更時はスクショやプレビュー URL を添付。
- 変更は小さく分割（1 記事 or 1 章単位）。未対応事項は本文ではなく PR 説明に TODO として明記。
