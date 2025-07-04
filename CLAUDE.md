# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## プロジェクト概要

このリポジトリはZenn CLIを使用したコンテンツ管理リポジトリです。Zennは日本の技術記事投稿プラットフォームで、このリポジトリにはMarkdown形式で書かれた記事や本が含まれています。

## Zenn CLIセットアップ

### 前提条件
- Node.js 14以上が必要（現在のバージョン: 23.5.0）

### 初期セットアップ
```bash
# プロジェクトの初期化（既に完了済み）
npm init --yes

# Zenn CLIのインストール（既に完了済み）
npm install zenn-cli

# Zennプロジェクトの初期化（既に完了済み）
npx zenn init
```

### 現在の状態
- zenn-cli バージョン: 0.1.162
- articles/ と books/ ディレクトリが作成済み

### アップデート方法
```bash
npm update zenn-cli
```

## よく使用するコマンド

### コンテンツ管理
- `npx zenn new:article` - 新しい記事を作成
- `npx zenn new:article --slug 記事のスラッグ --title タイトル --type idea --emoji ✨` - オプション指定で記事を作成
- `npx zenn new:book` - 新しい本を作成
- `npx zenn preview` - ローカルプレビューサーバーを起動してコンテンツを確認
- `npx zenn list:articles` - 全記事を一覧表示
- `npx zenn list:books` - 全書籍を一覧表示

### プレビューと公開
- `npx zenn preview` - ローカルプレビューサーバーを起動（http://localhost:8000）
- `npx zenn init` - ディレクトリでZenn CLIを初期化
- 連携されたGitHubリポジトリにプッシュすることでコンテンツが公開されます

### その他の便利なコマンド
- `npx zenn --version` - Zenn CLIのバージョン確認
- `npm update zenn-cli` - Zenn CLIをアップデート

## リポジトリ構造

- `articles/` - 個別の技術記事をMarkdown形式で格納
- `books/` - 書籍コンテンツを格納（現在は空）
- 各記事はユニークなIDをファイル名として使用（例：`1a2cdb4c5774af.md`）

## 記事フォーマット

記事は以下の構造のYAMLフロントマターを使用します：
```yaml
---
title: "記事タイトル"
emoji: "🧞‍♂️"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["トピック1", "トピック2"]
published: false # 公開するにはtrueに設定
---
```

## 記事スラッグの仕様

- スラッグはa-z0-9、ハイフン（-）、アンダースコア（_）の12〜50文字の組み合わせ
- 記事作成時に `--slug` オプションでスラッグを指定可能
- 既存記事のファイル名もこの仕様に従ってリネームする必要があります

## 重要なポイント

- このリポジトリの記事は日本語で執筆する必要があります
- 記事を公開するには、フロントマターで `published: true` に設定します
- リポジトリはGitHubと連携されており、自動デプロイされます
- 公開前にローカルでコンテンツをプレビューするには `npx zenn preview` を使用します