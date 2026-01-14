# AI Tools Release Watcher

Claude Code, Antigravity などのAIツールの更新を定期的にチェックし、新しいバージョンが出たらDiscordに通知する自動化スクリプトです。

## 仕組み
- GitHub Actionsのスケジュール機能で、6時間ごとに自動実行されます。
- `versions.json` に前回のバージョンを保存し、変更があった場合のみ通知します。
- 通知はDiscordのWebhookを使用します。

## 設定手順

### 1. Discord Webhookの取得
1. 通知したいDiscordチャンネルの「設定（歯車アイコン）」を開く
2. 「連携サービス」→「ウェブフック」→「新しいウェブフック」
3. 「ウェブフックURLをコピー」をクリック

### 2. GitHubリポジトリの作成
1. GitHubで新しいリポジトリを作成（例: `release-watcher`）
2. 作成したリポジトリの「Settings」タブを開く
3. 「Secrets and variables」→「Actions」→「New repository secret」
4. **Name**: `DISCORD_WEBHOOK_URL`
5. **Secret**: (手順1でコピーしたURLを貼り付け)
6. 「Add secret」をクリック

### 3. コードのアップロード
ターミナルで以下のコマンドを実行して、このフォルダをGitHubにアップロードしてください。

```bash
cd /Users/kiyohirowatanabe/Desktop/obsidian/99_Experiments/release-watcher
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/release-watcher.git
git push -u origin main
```
※ `YOUR_USERNAME` はあなたのGitHubユーザー名に置き換えてください。
