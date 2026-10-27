# Yuya Matsumoto（松本 侑也）

### Pythonバックエンドエンジニア志望

**医療現場の業務負担を減らすため、Pythonで勤務表作成支援ツールを個人開発しています。**

略歴：作業療法士（リハビリ専門職）として約6年半、回復期・急性期の医療に携わってきました（現職。2026年12月末に退職予定）。現場では、記録の作成や情報共有に時間を要することが多く、業務効率化を目的に導入されたツールでも、業務の流れに合わなければ次第に使われなくなる場面を見てきました。この経験から、現場の業務を理解したうえで、人が判断に集中できる仕組みを自ら作りたいと考え、2026年2月頃から独学を始めました。現在はPythonを使った開発とテストに取り組んでいます。

**希望勤務地：福岡県**

---

## 📂 ポートフォリオ

### [勤務表作成支援ツール](https://github.com/thousand-boy/kinmu-automation)

**Excelの職員情報と勤務希望から、勤務表の下書きを作るツールです。**

※公開サンプルは、職場で実際に使われている勤務表の形式をもとに、個人情報をすべて取り除いて作成したものです。

[使い方・サンプル](https://github.com/thousand-boy/kinmu-automation#readme) ｜ [実装コード](https://github.com/thousand-boy/kinmu-automation/tree/main/src/kinmu) ｜ [テスト](https://github.com/thousand-boy/kinmu-automation/tree/main/tests)

希望休を反映すると、別の日の人数や他の職員の連勤にも影響します。こうした調整の負担を減らすことが開発の目的です。

**処理の流れ**  
`Excel読込 → 入力検証 → 勤務割当 → Excel出力・保存後の検証`

#### 実装内容

- **条件の整理**：勤務ルールを「必ず守る条件」「できるだけ満たす条件」「人が判断する条件」に分けました。すべてを自動で決めず、最終判断は担当者が行う設計です。
- **勤務割当**：複数の条件を同時に扱うため、OR-Tools（CP-SAT）を使用。理由付きの固定予定・必要休日数・日曜の各病棟2名を必須とし、その他の人数・役割の目安はできるだけ満たす条件として扱います。重要な条件ほど優先されるよう評価の重みを設計し、テストで確認しています。
- **Excel処理**：現場のExcelを活かすため、openpyxlで読み書きします。職員追加時の行作成や、在籍対象外の職員を最適化・集計から除く処理もあります。
- **検証**：一時ファイルに保存して再読み込みし、数式・固定予定・休日数などを確認してから出力を置き換えます（失敗時は前回の出力を残します）。pytestによる99件のテストでは、職員変更・入力不備・保存失敗などを検証しています（統合2件を含む、2026年9月28日時点）。

確認や調整が必要な配置結果を表示します。コードはGitで管理し、GitHub Actionsによるテスト自動実行も設定しています。

> **現在は条件・動作を検証する試作品です。** 出力は担当者が確認・調整する前提で、現場での継続運用や時間削減効果は未検証です。

#### 開発の進め方

勤務条件を整理し、サンプルで職員の追加・在籍変更を試しながら、出力Excelやテストで動作を確認しています。

独学で初めての個人開発のため、疑問点の整理や実装・修正案の検討にはAI（ChatGPT、Claude）も活用しています。提案は業務条件と照合し、理解が曖昧な箇所は資料とコードを読み直しています。

詳しい条件・対応範囲はリポジトリのREADMEにまとめています。

---

## 🛠️ 技術スタック

言語・業務自動化・テスト・開発ツールは、勤務表ツールの個人開発で使用しています。エンジニアとしての実務経験はありません。

### 言語

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)

### 業務自動化・最適化

![OR-Tools](https://img.shields.io/badge/OR--Tools-4285F4?style=flat-square)
![openpyxl](https://img.shields.io/badge/openpyxl-217346?style=flat-square)

### テスト・開発ツール

![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

### フロントエンド（基礎学習・演習）

![HTML](https://img.shields.io/badge/HTML-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-663399?style=flat-square&logo=css&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

### 今後の学習・実装候補

![FastAPI](https://img.shields.io/badge/FastAPI-6B7280?style=flat-square&logo=fastapi&logoColor=white)
![REST API](https://img.shields.io/badge/REST_API-6B7280?style=flat-square)
![SQL](https://img.shields.io/badge/SQL-6B7280?style=flat-square)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-6B7280?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-6B7280?style=flat-square&logo=docker&logoColor=white)
![LLM API](https://img.shields.io/badge/LLM_API-6B7280?style=flat-square)

Pythonの処理・テスト・設計は、使用したコードを読み直しながら学習を続けています。

### 次の開発計画

1. **基礎知識の体系的な習得（2026年11月）**：基本情報技術者試験の学習に集中し、アルゴリズム・データベース・ネットワーク・セキュリティなどの基礎を固めます。
2. **言語化支援Webアプリの試作（2026年12月〜2027年2月予定）**：FastAPI・PostgreSQL・pytestで、メモを保存・取得・更新するAPIを作ります。そのうえでLLM APIを使い、断片的なメモを「主張・懸念・次の行動」などに整理し、本人が確認してから文章にする仕組みを作ります。
3. **勤務表作成支援ツールの改善**：勤務条件や職員変更に対する動作を検証し、必要に応じてAPI化と、入力・実行・結果確認ができる画面を追加します。

API・データベース・Web画面を備えた成果物は未実装で、上記2で取り組みます。

---

## 🤝 開発に活かしたい経験

- **利用者の状況を把握する**：患者様の状態・生活背景・希望を整理し、支援計画に反映してきました。
- **優先順位を判断する**：急性期の6病棟を担当し、患者様の状態や退院に向けた課題から介入の順序を判断してきました。
- **関係者と認識をそろえる**：医師・看護師などとの支援方針の調整や、記録・発表による情報共有を経験しています。
- **仕組みで改善する**：書類確認の担当者と手順を見直し、確認漏れを月30件前後から7〜8件に減らしました。

---

## 🎯 キャリア目標

まずは**Pythonバックエンドの実務経験を積み、担当する処理の実装・テスト・改善に取り組むこと**を優先しています。

将来は、情報整理や言語化を支えるAIアプリケーションを、利用者の判断と意図を尊重する形で開発できるエンジニアを目指しています。機械学習は、必要になった段階で深めていきます。

現在は、独学と個人開発を続けながら就職活動を進めています。状況にもよりますが、Python・AI関連の職業訓練校への入校も検討中です。

---

## ✉️ 連絡先

[work.inside1210@gmail.com](mailto:work.inside1210@gmail.com)
