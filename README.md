# HelloProjectPortal Preview

ハロプロポータルの確認用GitHub Pagesです。

## 公開元

- 本体リポジトリ: `pandasan86/HelloProjectPortal`
- 対象ブランチ: `feature/20260805_blog-kentei-top-ui`
- このリポジトリは公開先の設定だけを管理します
- サイトのソースは本体リポジトリのfeatureブランチを正とします

## 更新方法

GitHub Actionsが次のタイミングで本体featureブランチを取得し、GitHub Pagesへ公開します。

- 5分ごとの定期実行
- Actions画面からの手動実行
- Pagesワークフロー変更時

プレビュー用リポジトリをローカルへcloneしたり、サイトファイルを手作業でコピーしたりしません。

## 本番反映

プレビュー確認済みの本体featureブランチを、本体リポジトリの`main`へマージします。本番用ファイルの再作成やコピーは行いません。
