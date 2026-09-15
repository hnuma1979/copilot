---
name: 'Java Instructions'
description: 'Javaコードに関する指示を記述するファイルです。'
applyTo: '**/*.java'
---

# Instructions
- コード規約は Google Java Style Guide に従ってください。
- クラス名は UpperCamelCase を使用してください。
```java
/** クラスの概要 **/
public class ClassName {}
```
- メソッド名は lowerCamelCase を使用してください。
```java
/** メソッドの概要 **/
public void methodName() {}
```
- 変数名は lowerCamelCase を使用してください。
```java
/** 変数の概要 **/
private String variableName;
```
- 定数名は UPPER_SNAKE_CASE を使用してください。
```java
/** 定数の概要 **/
public static final String CONSTANT_NAME = "value";
```
- パッケージ名はすべて小文字を使用してください。
```java
/** パッケージの概要 **/
package com.example.project.controller;
```
- FQDNは完全修飾クラス名（例：`com.example.project.controller.ClassName`）を使用しないでください。
- どうしても避けれない場合は使用しても構いませんが、原則として避けるようにしてください。
- `Javadoc` はクラス、メソッド、フィールドに必要に応じて記述してください。
- `package-private` 以下のメソッドには簡略化した `javadoc` を記述してください。

## コントローラー（ **Controller** ）
- `@Controller`, `@RequestMapping` をクラスの上に使用してください。
- `@Slf4j` は必要に応じてクラスの上に使用してください。
- メソッドには `@GetMapping`, `@PostMapping` などのマッピングアノテーションを使用してください。
- `@PostMapping` を使用する場合は `@Valid` を併用してください。
- `@PutMapping` を使用する場合は `@Valid` を併用してください。
- `@PatchMapping` を使用する場合は `@Valid` を併用してください。
- `BindingResult` は `@Valid` と併用して、バリデーション結果を受け取るために使用してください。
- `BindingResult` でエラー時は入力値を保持してください。
- `ApplicationContextAware` を実装して、`ApplicationContext` を取得してください。
- `@PostConstruct` を使用して、初期化処理を行ってください。
- `@ModelAttribute` を使用して、モデル属性を設定してください。（例えば選択項目内容）
- コアな処理はサービス層に記述してください。
- パッケージは `com.example.project.controller` のように、機能ごとに分けてください。

## コントローラーアドバイス（ **Controller Advice** ）
- `@ControllerAdvice` をクラスの上に使用してください。
- `@ExceptionHandler` を使用して、例外処理を行ってください。
- `@ModelAttribute` を使用して、共通のモデル属性を設定してください。（例えば全画面共通の選択項目内容）
- パッケージは `com.example.project.controller` のように、機能ごとに分けてください。

## サービス（ **Service** ）
- `@Service` をクラスの上に使用してください。
- `@Slf4j` は必要に応じてクラスの上に使用してください。
- `ApplicationContextAware` を実装して、`ApplicationContext` を取得してください。
- `@PostConstruct` を使用して、初期化処理を行ってください。
- パッケージは `com.example.project.service` のように、機能ごとに分けてください。

## リポジトリ（ **Repository** ）
- JPAを利用時は `@Repository` をクラスの上に使用してください。
- `interface` として定義してください。
- `CrudRepository<ENTITY, ID>` を継承してください。
- `ユニークインデックス`が設定されている場合は `findBy`、`existsBy` 系メソッドを定義してください。
- `インデックス`が設定されている場合は `findAllBy', `existsBy` 系メソッドを定義してください。
- パッケージは `com.example.project.repository` のように、機能ごとに分けてください。

## エンティティ（ **Entity** ）
- `@Data`, `@Builder`, `@NoArgsConstructor`, `@AllArgsConstructor`, `@Table(name = "table_name")` を使用してください。
- プライマリーキーが自動生成される場合は、`@Id` を使用してください。
- プライマリーキーが自動生成されない場合（外部キー＝主キー）は、`@Id` を使用しないでください。（更新対象とされる）
- フィールドには `@Column(name = "column_name")` を必要に応じて使用してください。
- 作成日時には `@ReadOnlyProperty` を使用してください。（更新不可、DBにより自動設定される）
- 更新日時には `@ReadOnlyProperty` を使用してください。（更新不可、DBにより自動設定される）
- 時間項目は `java.time パッケージ`のクラス（例：`LocalDateTime`, `LocalDate`, `LocalTime`）を使用してください。
- パッケージは `com.example.project.entity` のように、機能ごとに分けてください。

## DTO（ **Data Transfer Object** ）
- `@Data`, `@Builder`, `@NoArgsConstructor`, `@AllArgsConstructor` を使用してください。
- フィールドには `@JsonProperty("json_property_name")` を必要に応じて使用してください。
- パッケージは `com.example.project.dto` のように、機能ごとに分けてください。

## 入力フォーム（ **Form** ）
- `@Data`, `@Builder`, `@NoArgsConstructor`, `@AllArgsConstructor` を使用してください。
- `Validation アノテーション`（例：`@NotNull`, `@Size`, `@Email` など）をフィールドに必要に応じて使用してください。
- パッケージは `com.example.project.form` のように、機能ごとに分けてください。

## プロパティ（ **Property** ）
- `@ConfigurationProperties("app.propertyname")` を必要に応じて使用してください。
- 3段目以降（app.propertyname.subname 等）の場合は、インナークラスとして定義し、クラス名は `Subname` としてください。
- パッケージは `com.example.project.properties` のように、機能ごとに分けてください。

## コンフィギュレーション（ **Configuration** ）
- `@Configuration` をクラスの上に使用してください。
- `@Bean` を必要に応じて使用してください。
- パッケージは `com.example.project.config` のように、機能ごとに分けてください。

## ユーティリティ（ **Utility** ）
- パッケージ名は `com.example.project.util` のように、機能ごとに分けてください。
- 同類処理は同一クラス内にまとめてください。
- クラスは `final` とし、インスタンス化を防いでください。
- コンストラクタは `private` としてください。 
- コンストラクタは `new UnsupportedOperationException("This class cannot be instantiated")` を投げるようにしてください。
- 全てのメソッドは `public static` としてください。

## 文字コード
- ファイルの文字コードは UTF-8 を使用してください。