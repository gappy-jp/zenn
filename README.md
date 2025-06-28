# Zenn CLI

このリポジトリはZenn CLIを使用したコンテンツ管理リポジトリです。

## 必要な環境
- Node.js 14以上

## セットアップ

```bash
# 依存関係のインストール
npm install

# Zenn CLIの動作確認
npx zenn --version
```

## 基本的な使用方法

### 記事の作成
```bash
# 新しい記事を作成
npx zenn new:article

# オプション指定で記事を作成
npx zenn new:article --slug article-slug --title "記事タイトル" --type tech --emoji 🚀
```

### 本の作成
```bash
npx zenn new:book
```

### プレビュー
```bash
# ローカルでプレビューを開始
npx zenn preview

# ブラウザで http://localhost:8000 にアクセス
```

### 記事の管理
```bash
# 全記事を一覧表示
npx zenn list:articles

# 全書籍を一覧表示
npx zenn list:books
```

## ディレクトリ構造
```
.
├── articles/          # 記事ファイル（.md）
├── books/            # 書籍ディレクトリ
├── package.json
└── README.md
```

## 公開方法
GitHubリポジトリと連携されているため、変更をプッシュすることで自動的に公開されます。

## 参考リンク
* [📘 How to use](https://zenn.dev/zenn/articles/zenn-cli-guide)
* [📘 Zenn CLIをインストールする](https://zenn.dev/zenn/articles/install-zenn-cli)