# Yuya Matsumoto（松本 侑也）

### Pythonバックエンドエンジニア志望

**医療現場の業務負担を減らすため、Pythonで勤務表作成支援ツールを個人開発しています。**

略歴：前職は作業療法士（リハビリ専門職）として約6年間、回復期・急性期での医療に携わってきました。現場では、記録の作成や情報共有に時間を要する事が多く、業務効率化目的で導入されたツールは、業務の流れに合わなければ次第に使用されない場面が多くみられました。この経験をきっかけに、現場の課題を仕組みで解決する仕事に携わりたいと考え、2026年2月頃に独学を始め、現在はPythonを使った開発とテストに取り組んでいます。

**希望勤務地：福岡県**

---

## 📂 ポートフォリオ

### [勤務表作成支援ツール](https://github.com/thousand-boy/kinmu-automation)

**Excelの職員情報と勤務希望から、勤務表の下書きを作るツールです。**

※なお、Excelの勤務表は実際に職場で使用されており、個人情報などを全て取り除いたものです。

[使い方・サンプル](https://github.com/thousand-boy/kinmu-automation#readme) ｜ [実装コード](https://github.com/thousand-boy/kinmu-automation/tree/main/src/kinmu) ｜ [テスト](https://github.com/thousand-boy/kinmu-automation/tree/main/tests)

希望休を反映すると、別の日の人数や他の職員の連勤にも影響します。こうした調整の負担を減らすことが開発の目的です。

**処理の流れ**  
`Excel読込 → 入力検証 → 勤務割当 → Excel出力・保存後の検証`

#### 実装内容

- **勤務割当**：複数の条件を同時に扱うため、OR-Tools（CP-SAT）を使用。理由付きの固定予定・必要休日数・日曜の各病棟2名を必須とし、その他の人数・役割の目安はできるだけ満たす条件として扱います。
- **Excel処理**：現場のExcelを活かすため、openpyxlで読み書きします。職員追加時の行作成や、在籍対象外の職員を最適化・集計から除く処理もあります。
- **検証**：保存後のExcelを再読み込みし、数式・固定予定・休日数などを確認します。pytestによる99件のテストでは、職員変更・入力不備・保存失敗などを検証しています（統合2件を含む、2026年9月28日時点）。

確認や調整が必要な配置結果を表示します。コードはGitで管理し、GitHub Actionsによるテスト自動実行も設定しています。

> **現在は条件・動作を検証する試作品です。** 出力は担当者が確認・調整する前提で、現場での継続運用や時間削減効果は未検証です。

#### 開発の進め方

勤務条件を整理し、サンプルで職員の追加・在籍変更を試しながら、出力Excelやテストで動作を確認しています。

独学で始めての個人開発のため、疑問点の整理や実装・修正案の検討にはAI（ChatGPT、Claude）も活用しています。提案は業務条件と照合し、理解が曖昧な箇所は資料とコードを読み直しています。

詳しい条件・対応範囲はリポジトリのREADMEにまとめています。公開サンプルには匿名化したデータを使用しています。

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

Pythonの処理・テスト・設計は、使用したコードを読み直しながら学習を続けています。

### 次の開発計画

1. **中核処理の検証・改善**：勤務条件や職員変更に対する動作を確かめる。
2. **バックエンドの拡張**：必要に応じてAPI化・データ管理を追加する。
3. **操作画面の追加**：HTML・CSS・JavaScriptで、入力・実行・結果確認ができる画面を作る。

API・データベース・Web画面は未実装です。

---

## 🤝 開発に活かしたい経験

- **利用者の状況を把握する**：患者様の状態・生活背景・希望を整理し、支援計画に反映してきました。
- **優先順位を判断する**：急性期の6病棟を担当し、患者様の状態や退院に向けた課題から介入の順序を判断してきました。
- **関係者と認識をそろえる**：医師・看護師などとの支援方針の調整や、記録・発表による情報共有を経験しています。

---

## 🎯 キャリア目標

まずは**Pythonバックエンドの実務経験を積み、担当する処理の実装・テスト・改善に取り組むこと**を優先しています。

将来は、情報整理や言語化を支えるAIアプリケーションと、機械学習モデルの開発の両方に携わるAI/MLエンジニアを目指しています。

現在は、独学と個人開発を続けながら就職活動を進めています。状況にもよりますが、Python・AI関連の職業訓練校への入校も検討中です。

---

## ✉️ 連絡先

[work.inside1210@gmail.com](mailto:work.inside1210@gmail.com)
