# Yuya Matsumoto（松本 侑也）

### バックエンドエンジニア志望｜Java / Spring Boot

2020年4月から作業療法士として医療現場で勤務し、2026年2月にプログラミングの学習を始めました。  
現場で実際にあった業務課題を題材に、Webアプリと業務自動化ツールを個人開発しています。

- **Main**：Java / Spring Boot（Webバックエンド）
- **Automation**：Python / OR-Tools / openpyxl（勤務表作成の自動化）
- **Certification**：基本情報技術者試験（2026年11月受験予定）
- **Location**：Fukuoka, Japan

## About Me

医療現場では患者対応のほか、書類管理や業務の改善にも関わってきました。  
書類確認漏れの対策では、発生内容を分析し、確認の担当者と手順を見直して件数を減らしました（詳しくは Project 01 に記載）。

この経験を通して、人の注意力や努力だけに頼るのではなく、**ミスが起こりにくい仕組みを作りたい**と考えるようになったことが、エンジニアを目指したきっかけです。

エンジニアとしての実務経験はなく、独学と個人開発で学習中です。分からないことは調べて試し、うまくいかなければ直しながら進めています。

## Tech Stack

<p>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original.svg" alt="Java" title="Java" width="36" height="36" />&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/spring/spring-original.svg" alt="Spring Boot" title="Spring Boot" width="36" height="36" />&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg" alt="Python" title="Python" width="36" height="36" />&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original.svg" alt="PostgreSQL" title="PostgreSQL" width="36" height="36" />&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/git/git-original.svg" alt="Git" title="Git" width="36" height="36" />
</p>

| 分類 | 技術 | 学習・使用状況 |
| --- | --- | --- |
| **Main** | Java / Spring Boot | 最も重点的に学習中（Project 01） |
| **Automation** | Python / OR-Tools / openpyxl | Project 02 で使用 |
| **Database / API** | SQL / PostgreSQL / REST API | Javaでのバックエンド開発を通じて学習中 |
| **Testing** | JUnit / pytest | テストコードを書くために学習・使用（pytest は Project 02 で使用） |
| **Tools** | Git / GitHub / VS Code | 個人開発・コード管理で使用 |
| **Next** | Docker / CI/CD / AWS / 認証・認可 | 今後学習予定 |

扱う技術を増やすことより、まずは Java / Spring Boot での開発を深めることを優先しています。

## Projects

### 01. 書類確認漏れ防止Webアプリ

<!-- Repository URL を追加したら、上の見出しを次の形に変更してください
### [01. 書類確認漏れ防止Webアプリ](https://github.com/ユーザー名/リポジトリ名)
-->

| Status | Tech Stack | Repository |
| --- | --- | --- |
| 要件整理・設計中 | Java / Spring Boot / PostgreSQL / JUnit | <!-- Repository URL を追加 --> |

医療現場で経験した書類確認漏れの問題をもとに、**「誰が・何を・どこまで確認したか」をシステム上で管理する**Webアプリです。  
Java / Spring Boot でバックエンド開発を学ぶための題材でもあります。

#### 背景

以前の職場では、書類の確認漏れが月30件前後発生していました。発生内容を分析すると、次のような問題がありました。

- 漏れが特定の書類に集中している
- 確認担当者が明確になっていない
- 複数人で確認するため、責任の所在があいまいになる

そこで確認担当者と確認手順を整理し、確認漏れを月7〜8件程度まで減らしました。  
この改善はWebアプリを作る前に、業務の見直しによって行ったものです。

#### 予定している機能

- 書類の登録・編集・削除（CRUD）
- 確認担当者の管理
- 確認ステータスの更新と、未確認書類の一覧表示
- 変更履歴の保存

実装面では、REST API、PostgreSQL へのデータ保存、入力値のバリデーション、例外処理、JUnit による単体テストに取り組む予定です。

#### 開発の進め方

**課題整理 → 要件整理 → 設計 → 実装 → テスト → 改善** の流れを意識して開発しています。  
作って終わりにせず、次のことを README や Git の履歴に残していきます。

- なぜこの機能が必要か
- なぜこの設計にしたか
- どこで問題が起き、どう調べて、どう直したか

> 患者情報や職員の個人情報は使わず、すべて架空または匿名化したデータで開発します。

---

### 02. 勤務表作成自動化ツール

<!-- Repository URL を追加したら、上の見出しを次の形に変更してください
### [02. 勤務表作成自動化ツール](https://github.com/ユーザー名/リポジトリ名)
-->

| Status | Tech Stack | Repository |
| --- | --- | --- |
| 開発中 | Python / OR-Tools / openpyxl / pytest | <!-- Repository URL を追加 --> |

Excelで手作業している勤務表作成を、Python と数理最適化（OR-Tools）で自動化するツールです。

#### 背景

勤務表は、休日数や勤務希望、病棟ごとの必要人数、職種・役割の配置、連続勤務、曜日ごとの人数制限など、多くの条件を同時に満たす必要があります。  
これを人が一つずつ確認するのではなく、**勤務ルールをプログラム上の制約条件として定義し、条件を満たす勤務パターンを自動で探索する**仕組みを作っています。

#### 実装している内容

- **読み込み**：Excel勤務表、スタッフ情報、病棟情報、役割（専従・専任・作業療法士など）、スタッフごとの必要休日数
- **制約条件**：希望休・勤務希望など入力済みの勤務の固定、病棟ごとの必要人数、職種・役割の配置、連続勤務、曜日ごとの休日人数の上限
- **探索**：OR-Tools による勤務パターンの探索、条件が矛盾している場合の検出
- **出力**：作成結果の Excel 出力
- **テスト**：pytest によるテスト

#### 制約条件の例

```text
・入力済みの勤務希望は変更しない
・4日連続勤務を禁止
・半休または休日で連続勤務をリセット
・日曜日は各病棟2名を確保
・平日は各病棟に必要な役割のスタッフを配置
・曜日ごとに休日人数の上限を設定
```

#### このプロジェクトで学んでいること

Pythonの文法に加えて、**現場の勤務ルールを整理し、コンピュータが扱える条件に置き換える**ことを学んでいます。  
あわせて、処理を関数に分けた構成やエラー処理、pytest でのテストなど、保守しやすいコードを書くことにも取り組んでいます。

## Background

作業療法士として6年以上、回復期・急性期の医療に携わってきました。  
医療現場での「現状を観察する → 問題を整理する → 原因を考える → 改善する」という流れを、開発でも活かしたいと考えています。

| 医療現場での経験 | 開発で活かしたいこと |
| --- | --- |
| 書類確認漏れの原因分析と改善 | 問題を分解し、原因を特定する |
| 急性期で複数病棟を担当し、介入の優先順位を判断 | タスクの優先順位を整理する |
| 医師・看護師など多職種との連携（カンファレンス・退院支援） | チームで情報を共有しながら進める |
| 記録・報告書の作成 | README や設計資料を分かりやすく残す |
| 業務フローの改善 | 使う人の立場から要件を整理する |

## Career Goal

- **現在の目標**：Java / Spring Boot で、仕様の理解から実装・テストまでを自分で担当できるバックエンドエンジニアになる
- **次の段階**：REST API設計、DB設計、認証・認可、Docker、CI/CD、AWS、詳細設計・基本設計へと担当範囲を広げ、サービス全体を考えて設計・開発に関わる
- **長期的な目標**：Python / AI / ML / LLM にも領域を広げ、バックエンドとAIの両方を理解したうえで、AI機能をプロダクトに実装できる Software Engineer を目指す

## Contact

Email：[work.inside1210@gmail.com](mailto:work.inside1210@gmail.com)
