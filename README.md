```markdown
# Yuya Matsumoto（松本 侑也）

### Backend Engineer Candidate | Java / Spring Boot

医療現場での業務改善経験を活かし、  
**「人の注意力や手作業に依存する業務を、ソフトウェアで改善する」**ことをテーマに開発を学んでいます。

現在は **Java / Spring Bootを中心としたバックエンド開発**を重点的に学習しながら、  
実際の業務課題を題材にしたポートフォリオを制作しています。

- 🎯 **Focus**：Java / Spring Boot / Backend Development
- 🐍 **Automation**：Python / OR-Tools / openpyxl
- 📚 **Learning**：REST API / SQL / Database / Testing
- 📝 **Certification**：基本情報技術者試験（2026年11月受験予定）
- 📍 **Location**：Fukuoka, Japan
- 📫 **Contact**：[work.inside1210@gmail.com](mailto:work.inside1210@gmail.com)

---

## 👤 About Me

2020年4月から作業療法士として医療現場で勤務し、  
患者対応だけでなく、書類管理・業務フロー改善・多職種連携などにも取り組んできました。

その中で、書類確認漏れの原因を分析し、担当者や確認手順を見直すことで、  
**月30件前後発生していた確認漏れを7〜8件程度まで削減した経験**があります。

この経験から、

> 人が気をつけ続ける仕組みではなく、  
> ミスが起こりにくい仕組みそのものを作りたい。

と考えるようになり、2026年2月からプログラミング学習を開始しました。

現在は、**Java / Spring Bootを軸にWebバックエンド開発を学習し、Pythonでは業務自動化ツールを開発しています。**

> 現在はエンジニアとしての実務経験はなく、独学・個人開発を通して学習しています。  
> GitHubでは完成物だけでなく、設計理由・実装過程・課題と改善内容も記録していきます。

---

## 🛠 Tech Stack

| Category | Technologies |
| --- | --- |
| **Backend / Main** | Java / Spring Boot |
| **Automation** | Python / OR-Tools / openpyxl |
| **Database / API** | SQL / PostgreSQL / REST API |
| **Testing** | JUnit / pytest |
| **Web Basics** | JavaScript / HTML / CSS |
| **Development Tools** | Git / GitHub / VS Code |
| **Currently Learning** | CRUD / Validation / Exception Handling / Database Design |
| **Next** | Docker / CI/CD / AWS / Authentication & Authorization |

現在は技術を広く増やすことよりも、  
**Java / Spring Bootで「仕様を理解 → 実装 → テスト」まで自分で完結できる力を身につけること**を優先しています。

---

# 🚀 Projects

## 01. 書類確認漏れ防止Webアプリ

### Document Check Management Web Application

**医療現場で経験した書類確認漏れの問題を、Java / Spring Bootを使って仕組みで防ぐWebアプリとして再設計しています。**

**Status：要件整理・設計中**

### Background

以前の職場では、月30件前後の書類確認漏れが発生していました。

発生内容を分析したところ、

- 漏れが特定の書類に集中している
- 確認担当者が明確になっていない
- 複数人で確認することで責任の所在が曖昧になる

といった問題がありました。

そこで、確認担当者と確認手順を整理することで、  
**月30件前後あった確認漏れを7〜8件程度まで削減しました。**

現在はこの経験をもとに、

**「誰が・何を・どこまで確認したのかをシステム上で管理する」**

ことを目的としたWebアプリを制作しています。

### Planned Features

- 書類情報の登録・編集・削除
- 確認担当者の管理
- 確認ステータスの更新
- 未確認書類の一覧表示
- 変更履歴の保存
- 入力値のバリデーション
- エラーハンドリング
- REST API
- データベースへの永続化
- 単体テスト

### Tech Stack

```text
Java
Spring Boot
PostgreSQL
REST API
JUnit
Git / GitHub
```

### What I Focus On

単にアプリを完成させるのではなく、

```text
課題の整理
    ↓
要件定義
    ↓
設計
    ↓
実装
    ↓
テスト
    ↓
改善
```

という開発プロセスを理解することを重視しています。

特に、

- なぜこの機能が必要なのか
- なぜこの設計を選択したのか
- どこで問題が発生したのか
- どのように調査したのか
- どのように修正したのか

をREADMEやGitの履歴として残していく予定です。

> **Privacy**  
> 患者情報・職員の個人情報などは使用せず、すべて架空・匿名化したデータで開発します。

---

## 02. 勤務表作成自動化ツール

### Shift Scheduling Automation Tool

**Excelで手作業している勤務表作成を、Pythonと数理最適化を使って自動化するツールを開発しています。**

**Status：開発中**

### Background

勤務表の作成では、

- スタッフごとの休日数
- 勤務希望
- 病棟ごとの必要人数
- 職種・役割ごとの配置
- 連続勤務
- 曜日ごとの人数制限

など、多くの条件を同時に確認する必要があります。

これらを人が一つずつ確認するのではなく、  
**勤務ルールをプログラム上の制約条件として定義し、自動で勤務パターンを作成できる仕組み**を開発しています。

### Current Features

- Excel勤務表の読み込み
- スタッフ情報の取得
- 病棟・役割情報の取得
- 希望休・勤務希望などの固定
- 必要休日数の取得
- 勤務条件の制約化
- OR-Toolsによる勤務パターンの探索
- 条件矛盾の検出
- 作成結果のExcel出力

### Example Constraints

```text
・入力済みの勤務希望は変更しない
・4日連続勤務を禁止
・半休または休日で連続勤務をリセット
・日曜日は各病棟2名を確保
・平日は各病棟に必要な役割のスタッフを配置
・曜日ごとに休日人数の上限を設定
```

### Tech Stack

```text
Python
OR-Tools
openpyxl
pytest
Git / GitHub
```

### What I Am Learning

このプロジェクトではPythonの文法だけではなく、  
**現実の業務ルールをプログラムが処理できる条件へ変換すること**を重視しています。

特に、

- 関数への処理分割
- 条件分岐・繰り返し処理
- リスト・辞書によるデータ管理
- Excelデータの読み書き
- 制約条件の設計
- 数理最適化
- エラー処理
- テスト
- 保守しやすいコード構成

を実践しています。

---

# 💼 Background

## Occupational Therapist → Software Engineer

作業療法士として6年以上、回復期・急性期医療に携わってきました。

急性期では複数病棟を担当し、患者の状態・治療予定・退院予定などを確認しながら、  
限られた時間の中で介入の優先順位を判断していました。

また、

- 多職種カンファレンス
- 退院支援
- 書類管理
- 業務改善
- 勉強会運営

などにも携わりました。

### Experience → Engineering

| Experience | Engineeringで活かしたいこと |
| --- | --- |
| 書類確認漏れの原因分析・改善 | 問題を分解し、原因を特定する |
| 複数病棟での優先度判断 | タスクの優先順位を整理する |
| 医師・看護師などとの多職種連携 | チームで情報を共有しながら進める |
| 記録・報告書の作成 | README・設計資料を分かりやすく残す |
| 業務フロー改善 | 利用者視点から要件を整理する |

医療現場で身につけた、

**「現状を観察する → 問題を整理する → 原因を考える → 改善する」**

という考え方を、ソフトウェア開発にも活かしていきたいと考えています。

---

# 🎯 Career Goal

まずは **Java / Spring Bootを中心としたバックエンドエンジニア**として、

```text
仕様を理解する
    ↓
実装する
    ↓
テストする
    ↓
改善する
```

という一連の開発を、自立して担当できるようになることが目標です。

その後は、

**REST API / DB設計 / 認証・認可 / Docker / CI/CD / AWS**

などへ担当範囲を広げ、  
バックエンドだけでなくサービス全体を考えて設計・開発できるエンジニアを目指します。

将来的にはPythonやAI / MLにも専門領域を広げ、

**バックエンドとAIの両方を理解し、AI機能を実際のプロダクトとして実装できるSoftware Engineer**

になることを長期的な目標としています。

---

## 📚 Currently Learning

```text
Java
└── Spring Boot
    ├── REST API
    ├── CRUD
    ├── SQL / PostgreSQL
    ├── Validation
    ├── Exception Handling
    └── JUnit

Python
└── Automation
    ├── OR-Tools
    ├── openpyxl
    └── pytest

Computer Science
└── 基本情報技術者試験
```

---

### 📫 Contact

**Email**  
[work.inside1210@gmail.com](mailto:work.inside1210@gmail.com)
```
