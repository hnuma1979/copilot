---
description: build.gradleファイルのコードスタイルに関する指示です。
applyTo: **/build.gradle
---

## コードスタイル
- インデントはスペース2つを使用してください。
- 文字コードは UTF-8 を使用してください。
- dependenciesブロック内にバージョン情報は記載せずに dependency management を使用してください。
```gradle
dependencyManagement {
	imports {
		mavenBom 'org.testcontainers:testcontainers-bom:1.20.6'
	}
	dependencies {
		dependency 'org.webjars:bootstrap:5.3.3'
	}
}
```
## 依存関係分類
- 依存関係の記述はアルファベット順に並べてください。
- 依存関係は以下のように分類してください。
  - implementation: 実行時に必要な依存関係
  - compileOnly: コンパイル時にのみ必要な依存関係
  - runtimeOnly: 実行時にのみ必要な依存関係
  - annotationProcessor: アノテーションプロセッサの依存関係
  - developmentOnly: 開発時にのみ必要な依存関係
  - testImplementation: テスト時に必要な依存関係
  - testAnnotationProcessor: テスト時のアノテーションプロセッサの依存関係
  - testCompileOnly: テストコンパイル時にのみ必要な依存関係
  - testRuntimeOnly: テスト実行時にのみ必要な依存関係
  - testDevelopmentOnly: テスト時の開発時にのみ必要な依存関係
- 依存関係の分類は、上記の順序に従って記述してください。

## 文字コード
- ファイルの文字コードは UTF-8 を使用してください。