# Claude Code Guidelines for Study Sessions

このプロジェクトは、強会用の資料およびデモコードを管理するためのリポジトリです。
資料作成には **Marp** を使用し、GitHub Pages での公開および PDF でのアーカイブ化を前提としています。

## 1. プロジェクト構造と命名規則

新しい勉強会の作成を指示された際は、以下のディレクトリ構造に従ってください。

- ルートディレクトリ: `sessions/`
- フォルダ命名規則: `YYYY-MM-DD_トピック名` (例: `sessions/2026-01-02_ruby-intro`)

### ディレクトリ内部構成
作成する各セッションフォルダ内には、以下のファイルを含めてください。

- `slides.md`: スライド本体（Marp形式）
- `assets/`: 画像資材（必要に応じて）
- `demo/`: デモコード（ブラウザ完結型を推奨）
- `README.md`: 勉強会の概要、参照URL、実行手順などを記載

## 2. スライド作成ガイドライン (Marp特化)

スライドは全て **Marp** で記述します。
新規作成時は、`slides.md` の冒頭に以下の Frontmatter (設定ブロック) を必ず含めてください。

```yaml
---
marp: true
theme: gaia
paginate: true
header: "勉強会タイトル | 氏名"
footer: "© 2026 ponpon.USA"
---
```

### スライド構成のベストプラクティス
- **タイトルスライド**: タイトル、日付、発表者名
- **アジェンダ**: 本日の流れ
- **本編**:
  - 箇条書きとコードブロックを主体にする
  - 図解が必要な場合は Mermaid 記法の利用を検討する
  - 画像は `![bg right:40%](path/to/image.png)` 等の記法で配置調整を行う
- **デモ**: デモの実施ポイントや手順へのリンク
- **まとめ**: Key Takeaways
- **参照リンク**: GitHubリポジトリや参考記事のURL

## 3. GitHub Pages デプロイ運用

GitHub Actions を利用して、Markdown を HTML に変換して公開します。

### デプロイ設定 (Action)
`.github/workflows/deploy.yml` の運用ルールは以下の通りです。

- **使用ツール**: `marp-cli` (公式Action `marp-team/marp-cli-action` 推奨)
- **トリガー**: `main` ブランチへの push
- **出力**: `sessions/` 配下のすべての `.md` ファイルを HTML に変換
- **公開**: `gh-pages` ブランチへデプロイ

## 4. 行動指針

- **機密情報の排除**: 生成する資料やコードには、特定の企業名、プロジェクト名、認証情報（API Key等）を含めないでください。一般的な技術用語を使用してください。
- **ブラウザ完結**: デモコードは可能な限り `GitHub Codespaces` やブラウザ上で動作する構成を優先し、ローカル環境依存を減らしてください。
