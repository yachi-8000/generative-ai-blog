# Generative AI Blog

Docusaurusで構築するブログサイトです。Dockerで静的配信し、GitHub Pagesで公開します。スマホからも閲覧可能です。

## 前提

- Node.js 20
- Docker / Docker Compose
- GitHub Actions を利用した Pages 公開

## ローカル（Dockerで静的配信）

```bash
docker compose up --build
```

- PC: `http://localhost:3000/generative-ai-blog/`
- スマホ（同一LAN）: `http://<PCのIPアドレス>:3000/generative-ai-blog/`

停止:

```bash
docker compose down
```

## ローカル（開発サーバー）

```bash
npm ci
npm run start -- --host 0.0.0.0 --port 3000
```

- PC: `http://localhost:3000/`
- スマホ（同一LAN）: `http://<PCのIPアドレス>:3000/`

## ビルド

```bash
npm run build
```

成果物は `build/` に出力されます。

## GitHub Pages デプロイ

`main` ブランチへの push で GitHub Actions が自動デプロイします。

公開URL:

- `https://yachi-8000.github.io/generative-ai-blog/`

必要な設定:

- GitHub リポジトリの `Settings → Pages → Source` を **GitHub Actions** に設定

## Docs（拡張用）

Docs 機能は有効ですが、ナビ/フッターからは非表示です。アクセスする場合は下記のURLです。

- `https://yachi-8000.github.io/generative-ai-blog/docs/`

## VS Code タスク

`.vscode/tasks.json` にタスクを用意しています。

- `Docker: Build + Up`
- `Docker: Down`
- `NPM: Install`
- `NPM: Dev Server`
- `NPM: Build`

VS Code のコマンドパレットで `Tasks: Run Task` を実行して選択できます。
