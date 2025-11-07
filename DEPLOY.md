# GitHub Pagesへのデプロイ手順

## 1. GitHub認証の設定

### 方法A: Personal Access Tokenを使用（推奨）

1. GitHubにログイン
2. Settings > Developer settings > Personal access tokens > Tokens (classic)
3. "Generate new token" をクリック
4. 以下の権限を選択：
   - `repo` (すべてのリポジトリへのアクセス)
5. トークンを生成してコピー

### 方法B: SSHキーを使用

1. SSHキーを生成（まだの場合）:
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```

2. SSHキーをGitHubに追加:
   - Settings > SSH and GPG keys > New SSH key

## 2. リモートURLの設定

### Personal Access Tokenを使用する場合:
```bash
git remote set-url origin https://YOUR_TOKEN@github.com/cross-support/Production-Management-Level-3-Coverage-Analysis-Report.git
```

### SSHを使用する場合:
```bash
git remote set-url origin git@github.com:cross-support/Production-Management-Level-3-Coverage-Analysis-Report.git
```

## 3. プッシュ

```bash
git push -u origin main
```

## 4. GitHub Pagesの有効化

1. GitHubリポジトリのページにアクセス
2. Settings > Pages
3. Source: "Deploy from a branch" を選択
4. Branch: `main` を選択
5. Folder: `/ (root)` を選択
6. Save をクリック

数分後、以下のURLでレポートが公開されます：
https://cross-support.github.io/Production-Management-Level-3-Coverage-Analysis-Report/

## 注意事項

- CSVファイルは同じディレクトリに配置されている必要があります
- ブラウザのCORS制限により、CSVファイルの読み込みにはGitHub PagesのURLが必要です

