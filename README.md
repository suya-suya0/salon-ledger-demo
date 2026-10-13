# Salon Ledger — バージョンファイル追加で自動公開

GitHub Pages 用の試作版です。**顧客の実データは入れないでください。**

## 初回セットアップ

1. GitHubで新しい公開リポジトリ（例：`salon-ledger-demo`）を作成します。`main` ブランチを使用してください。
2. このZIPを展開して、`index.html`、`index_v2.html`、`.github/workflows/auto-latest.yml` を **同じ階層構造のまま** リポジトリにアップロード／コミットします。
   - GitHubのWeb画面で隠しフォルダ `.github` がアップロードしにくければ、`Add file → Create new file` で `.github/workflows/auto-latest.yml` と入力して、同梱のファイル内容を貼り付けて保存できます。
3. GitHubリポジトリの `Settings → Pages → Build and deployment → Source` を **GitHub Actions** に設定してください（以前の Deploy from a branch とは異なります）。
4. `Settings → Actions → General → Workflow permissions` で、必要なら **Read and write permissions** を選び保存します。組織のポリシーで許可されない場合は管理者に相談してください。
5. `Actions → Auto publish latest Salon Ledger → Run workflow` で初回実行します。成功するとPagesの公開URLが表示されます。

## v3以降の更新方法

1. 新しいHTMLを `index_v3.html`、`index_v4.html`、`index_v4.1.html` という名前にしておきます。
2. GitHubのリポジトリ直下に **追加アップロードしてコミットするだけ**。
3. 自動処理が数字上で最大のファイルを選び、`index.html` にコピーしてコミットし、GitHub Pagesへ公開します。
4. 友達は **同じURL** を開いて最新版を確認できます。反映には通常少し時間がかかります。

過去の `index_v2.html` などは消さずに履歴として残ります。ファイル名では `index_v10.html` は `index_v9.html` より新しく判定されます。`index_v2.3.html` も利用できます。単なる `index.html` の追加では自動判定の対象外です。デプロイ前に更新したファイルがHTMLとして問題なく動作するかは別途テストしてください。

### 注意
- GitHub Pagesは公開サイトです。実名、連絡先、支払情報等の個人情報は入力しないでください。
- この試作アプリの保存はブラウザ内のローカル保存であり、端末間の同期はできません。
- `index.html` を自動コミットするため、ワークフローにはリポジトリの書き込み権限が必要です。
- 本番利用にはログイン・権限・データベース・監査ログ等が別途必要です。
