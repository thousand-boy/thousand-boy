# Yuya Matsumoto（松本 侑也）

### Pythonバックエンドエンジニア志望

**現場で使われ続ける仕組みを作るため、Pythonで勤務表作成支援ツールを個人開発しています。**

略歴：作業療法士として約6年半、回復期・急性期の病院に勤務しています（2026年12月末退職予定）。回復期病院では、スタッフと作り込んだExcelのチェックリストで書類の確認漏れを月約50件から7〜8件に減らした一方、業務の流れに合わず使われなくなるツールも見てきました。この経験から、仕組みを自分で作り、直し、使われる状態まで持っていく側に回りたいと考え、2026年2月からPythonを独学しています。

**希望勤務地：福岡県　／　入社可能時期：2027年1月**

---

## 📂 ポートフォリオ

### [勤務表作成支援ツール](https://github.com/thousand-boy/kinmu-automation)

**Excelの職員情報と勤務希望から、勤務表の下書きを作るツールです。**

希望休を反映すると、別の日の人数や他の職員の連勤にも影響します。こうした調整の負担を減らすことが開発の目的です。

[使い方・サンプル](https://github.com/thousand-boy/kinmu-automation#readme) ｜ [実装コード](https://github.com/thousand-boy/kinmu-automation/tree/main/src/kinmu) ｜ [テスト](https://github.com/thousand-boy/kinmu-automation/tree/main/tests)

※公開サンプルは、職場で使われている勤務表の形式をもとに、個人情報をすべて取り除いて作成したものです。

**処理の流れ**  
`Excel読込 → 入力検証 → 勤務割当 → Excel出力・保存後の検証`

#### 実装内容

- **条件の整理**：勤務ルールを「必ず守る」「できるだけ満たす」「人が判断する」の3種類に分けました。すべてを自動で決めず、最終判断は担当者が行う設計です。
- **勤務割当**：複数の条件を同時に扱うため、OR-Tools（CP-SAT）を使用しています。固定予定・必要休日数・日曜の各病棟2名を必須とし、それ以外の人数や役割の目安はできるだけ満たす条件として扱います。重要な条件ほど優先されるよう評価の重みを設計し、テストで確認しています。
- **Excel処理**：現場のExcelを活かすため、openpyxlで読み書きします。openpyxlの行挿入では数式の参照が補正されないため、参照・結合セル・入力規則などを補正する処理を実装しました。
- **検証**：一時ファイルに保存して再読み込みし、数式・固定予定・休日数などを確認してから出力を置き換えます（失敗時は前回の出力を残します）。
- **テスト**：pytestで99件（統合2件を含む、2026年9月28日時点）。職員変更・入力不備・保存失敗などを確認し、GitHub Actionsでpush時に自動実行しています。

> **現在は条件と動作を検証する試作品です。** 出力は担当者が確認・調整する前提で、現場での継続運用や時間削減の効果は未検証です。

#### 開発の進め方

サンプルで職員の追加や在籍変更を試しながら、出力Excelとテストで動作を確認しています。疑問点の整理や実装案の検討にはAI（ChatGPT、Claude）も活用し、提案は業務条件と照合したうえで、理解してから取り入れています。

詳しい条件と対応範囲は、リポジトリのREADMEにまとめています。

---

## 🛠️ 技術スタック

言語・最適化・テスト・開発ツールは、勤務表ツールの個人開発で使用しています。エンジニアとしての実務経験はありません。

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

### 次の開発計画

1. **基礎知識の習得（2026年11月）**：基本情報技術者試験の学習に集中し、アルゴリズム・データベース・ネットワーク・セキュリティの基礎を固めます。
2. **言語化支援Webアプリの最小版（2026年12月予定）**：FastAPI・PostgreSQL・pytestでメモを保存・取得・更新するAPIを作り、LLM APIで断片的なメモを「主張・懸念・次の行動」などに整理して、本人の確認後に文章化する仕組みを公開します。
3. **勤務表作成支援ツールの改善（継続）**：動作の検証を続け、必要に応じてAPI化と操作画面の追加を行います。

API・データベース・Web画面を備えた成果物は未実装で、上記2で取り組みます。

---

## 🤝 開発に活かしたい経験

- **使われ続ける仕組みを作る**：回復期病院で、スタッフへの聞き取りをもとにExcelのチェックリストと評価記録のテンプレートを作成しました。リハビリスタッフ30名全員が閲覧・記入できる形と定期確認の運用を整え、書類の確認漏れを月約50件から7〜8件に減らしました。
- **伝わる形に整える**：医師・看護師などと支援方針をすり合わせてきました。スタッフのカルテ記録の確認も担当し、表現の修正や代替案を提案してきました。
- **優先順位を判断する**：急性期の6病棟を担当し、患者様の状態や退院に向けた課題から介入の順序を判断してきました。
- **利用者の状況を把握する**：患者様の状態・生活背景・希望を整理し、支援計画に反映してきました。

---

## 🎯 キャリア目標

まずは**Pythonバックエンドの実務で、担当する処理の実装・テスト・改善を確実に担えるようになること**を目指しています。

将来は、情報整理や言語化を支えるAIアプリケーションを、利用者の判断と意図を尊重する形で開発できるエンジニアを目指しています。機械学習は、必要になった段階で深めていきます。

現在は、2027年1月の入社に向けて、学習と個人開発を続けながら就職活動を進めています。

---

## ✉️ 連絡先

[work.inside1210@gmail.com](mailto:work.inside1210@gmail.com)
