# HelloProjectPortal Preview

ハロプロポータルのfeatureブランチを確認するためのGitHub Pages公開専用リポジトリです。

## プレビューURL

https://pandasan86.github.io/-HelloProjectPortal-Preview/

## 現在の公開元

- 本体リポジトリ: `pandasan86/HelloProjectPortal`
- 対象ブランチ: `main`
- 現在の確認内容: 次のfeature作業開始前の待機状態
- サイト実装の正しいソース: 本体リポジトリの対象ブランチ
- このリポジトリ: Pagesワークフローと更新トリガーだけを管理する公開先

統合済みfeatureの確認完了後は、プレビュー公開元を `main` へ戻します。次の開発開始時に、新しいfeatureブランチへ切り替えます。

プレビュー側へHTML、CSS、JavaScript、JSON、画像を直接追加・修正しません。ChatGPTやCodexによる実装修正は、必ず本体リポジトリの対象ブランチへ反映します。

## 自動更新

GitHub Actionsが本体の対象ブランチを取得し、次の公開用ファイルだけをGitHub Pagesへ配置します。

- `index.html`
- `404.html`（存在する場合）
- `assets/`
- `character/`
- `games/`
- 公開元確認用 `preview-source.json`

`docs/`、`gas/`、`source-data/`、`tools/`、`AGENTS.md` などはプレビューへ公開しません。

更新契機:

- 5分ごとの定期確認
- Actions画面からの手動実行
- `refresh.json` 更新
- Pagesワークフロー変更

定期確認時に対象ブランチのコミットが前回公開時と同じ場合は、再デプロイを省略します。

## ローカル運用

プレビュー用リポジトリをローカルへcloneしません。サイトファイルを手作業でコピーしません。ローカルでは本体リポジトリだけを扱います。

## 本番反映

1. 本体featureブランチへ実装・修正する
2. プレビューURLで確認する
3. 自動テスト、ブラウザ検証、利用者の実機確認を完了する
4. 確認済みfeatureブランチを本体リポジトリの `main` へfast-forwardする
5. `main` のGitHub Pages本番URLを確認する
6. プレビュー公開元を `main` へ戻す

プレビュー確認済みの同じコミットを `main` へ取り込むため、本番用ファイルの再作成や手作業コピーは行いません。
