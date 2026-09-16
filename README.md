# Copilot AI Agent Plugin

このリポジトリは、GitHub Copilot AI Agent 向けのカスタム指示・プロンプト・スキルをまとめたプラグインです。

## 目的

- Java / JavaScript / HTML / CSS / SQL / Shell などのコードを安全かつわかりやすく扱う
- 日本語での説明を基本とし、初心者にも理解しやすい出力を促す
- Javadoc の生成やコードレビューの補助を行う

## 構成

- [plugin.json](plugin.json): プラグインの定義ファイル
- [instructions](instructions): 役割ごとの指示ファイル
- [prompts](prompts): よく使う Copilot 用プロンプト
- [skills/javadoc](skills/javadoc): JavaDoc 生成用スキル
- [.github/copilot-instructions.md](.github/copilot-instructions.md): Copilot Agent の全体ルール

## 主要ファイル

### 1. plugin.json

プラグイン自体のメタ情報と、登録する instruction / skill の一覧を定義します。

### 2. instructions/

各ファイル種別に対応した指示をまとめています。

- [instructions/all.instructions.md](instructions/all.instructions.md)
- [instructions/java.instructions.md](instructions/java.instructions.md)
- [instructions/javascript.instructions.md](instructions/javascript.instructions.md)
- [instructions/html.instructions.md](instructions/html.instructions.md)
- [instructions/css.instructions.md](instructions/css.instructions.md)
- [instructions/sql.instructions.md](instructions/sql.instructions.md)
- [instructions/shell.instructions.md](instructions/shell.instructions.md)
- [instructions/build.gradle.instructions.md](instructions/build.gradle.instructions.md)
- [instructions/properties.instructions.md](instructions/properties.instructions.md)
- [instructions/yml.instructions.md](instructions/yml.instructions.md)

### 3. prompts/

AI に特定の作業を依頼しやすくするためのプロンプトです。

- [prompts/explain-code.prompt.md](prompts/explain-code.prompt.md)
- [prompts/review-code.prompt.md](prompts/review-code.prompt.md)

### 4. skills/javadoc

Java コードの説明や Javadoc 生成に役立つスキルです。

## 想定される利用方法

1. Copilot Chat で、このリポジトリをワークスペースとして開く
2. [plugin.json](plugin.json) の定義に従って指示とスキルが利用される
3. 必要に応じて、以下のような依頼を実行する
   - 「このクラスを日本語でわかりやすく説明して」
   - 「このコードをレビューして改善案を出して」
   - 「JavaDoc を追加して」

## 注意事項

- 出力は基本的に日本語で行う
- 専門用語は必要最小限にし、必要時だけ補足説明をする
- 変更時は最小範囲で安全に行う
- 変更を完了したと主張する前に、関連する検証を行う

## 拡張の考え方

このプラグインは、プロジェクト固有のルールを追加しやすいように構成されています。
今後は以下を追加しやすくなっています。

- さらに詳細なドメイン別指示
- API 設計レビュー用のプロンプト
- テスト作成用のスキル
- CI / ビルドチェック用の指示
