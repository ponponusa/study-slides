---
marp: true
theme: classmethod
paginate: true
style: |
  .highlight-box {
    background-color: #e3f2fd;
    border-left: 4px solid #2196f3;
    padding: 32px 16px;
    margin: 48px 32px;
  }
  .red-accent-text {
    color: red;
    font-weight: 900;
  }
  .green-accent-text {
    color: green;
    font-weight: 900;
  }
  .blue-accent-text {
    color: blue;
    font-weight: 900;
  }
  section.table-center table {
    width: auto;
    margin: 0 auto;
  }
  section.table-font-large table {
    font-size: 22px;
  }
  .experiment-box {
    background-color: #fff3e0;
    border-left: 4px solid #ff9800;
    padding: 24px 16px;
    margin: 32px 32px;
  }
  .copilot-box {
    background-color: #e8f5e9;
    border-left: 4px solid #4caf50;
    padding: 24px 16px;
    margin: 32px 32px;
  }
---

<!-- _class: title -->
<!-- _paginate: false -->

![ponpon.USA w:150px](https://avatars.githubusercontent.com/u/238978340?v=4)
# AI Paired Engineer #1
## インターネットの世界観 — レストランと手紙

2026-03-16
ponpon.USA

---

<!-- _class: section -->
<!-- _paginate: false -->

## Phase 2 のはじまり

---

<!-- _class: no-header all-text-center align-center -->

# Phase 1 で「地図の読み方」を学んだ

<br>

### 鉄道のメタファーで、アーキテクチャの本質を掴んだ

<br>

## Phase 2 では
## **AIに指示して、出てきたものを観察し、納得する**

---

<!-- _class: no-header all-text-center align-center -->

# Phase 2 の共通ルール

<br>

<div class="highlight-box">
  <b>コードを書くのではない</b><br><br>
  AIに指示して、出てきたものを<span class="green-accent-text">観察</span>し、<span class="green-accent-text">納得</span>する<br><br>
  「わかった気になれた」＋<b>Copilotの機能を自力で使える</b>状態がゴール
</div>

---

<!-- _class: no-header all-text-center align-center -->

# 毎回の流れ — 3パート構成

<br>

<div class="highlight-box">
  <b>Part 1：</b>比喩で掴む — 今日のテーマを日常に置き換える<br><br>
  <b>Part 2：</b>Copilot機能を学ぶ — 新しい武器を手に入れる<br><br>
  <b>Part 3：</b>実験で確かめる — 手を動かして納得する
</div>

---

<!-- _class: no-header all-text-center align-center -->

# 今週のテーマ

<br>

# インターネットの世界観

<br>

### 目に見えない「通信」のやり取りを
### 物理的な「モノの移動」として脳内変換する

---

<!-- _class: no-header all-text-center align-center table-center table-font-large -->

# 今週の Copilot スキルツリー

<br>

| Day | テーマ | 習得する Copilot 機能 |
|---|---|---|
| **1** | プロンプトの基礎 | 基本チャット、モデル選択 |
| **2** | HTTP通信 | `/explain`、`#selection` |
| **3** | Front / Back | `@workspace`、`#file` |
| **4** | DB / CRUD | Agent Mode、`/new` |
| **5** | Webの仕組み | Copilot Edits（Edit Mode） |

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 1：AI活用 — プロンプトの基礎

---

<!-- _class: no-header all-text-center align-center -->

# 今日の比喩

<br>

# 魔法のランプの魔人

<br>

### 具体的にお願いしないと
### **変な叶え方をする**

---

<!-- _class: no-header all-text-center align-center -->

# 曖昧な願い vs 具体的な願い

<br>

<div class="highlight-box">
  <b>曖昧：</b>「カレーの作り方を教えて」<br>
  → どんなカレー？ 誰が？ 時間は？ 材料は？<br><br>
  <b>具体：</b>「一人暮らしの男性が、15分以内に、<br>
  コンビニ食材だけで作れるカレーのレシピを教えて」<br>
  → <span class="green-accent-text">回答の質が劇的に変わる</span>
</div>

---

<!-- _class: no-header all-text-center align-center -->

# 今日の Copilot 機能

<br>

<div class="copilot-box">
  <b>基本チャット</b> — Copilot Chat パネルで自由に質問<br><br>
  <b>モデル選択</b> — GPT-4o / Claude / Gemini を切り替えられる<br><br>
  モデルにも「個性」がある。用途で使い分ける
</div>

---

<!-- _class: no-header all-text-center align-center -->

# ハンズオン

<br>

<div class="experiment-box">
  <b>Part 1（5分）：曖昧 vs 具体の体験</b><br>
  「カレーの作り方を教えて」→ 回答を確認<br>
  「一人暮らしの男性が、15分以内に...」→ 回答の質の差を比較<br><br>
  <b>Part 2（10分）：モデルの切り替え体験</b><br>
  同じプロンプトを GPT-4o → Claude Sonnet で実行<br>
  回答のスタイルの違いを観察する<br><br>
  <b>Part 3（5分）：コンテキストの段階的追加</b><br>
  「Webアプリを作りたい」（曖昧）→<br>
  「初心者が、Todoアプリを、HTML/JSだけで...」（具体）
</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 1 の気づき

<br>

<div class="highlight-box">
  AIは <span class="red-accent-text">「察してくれない」</span> パートナー<br><br>
  具体的な指示（<b>コンテキスト</b>）を与えるほど、<br>
  回答の精度が上がる<br><br>
  これは今後の <b>すべての実験の基礎</b> になる
</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 2：HTTP通信 — Client / Server

---

<!-- _class: no-header all-text-center align-center -->

# 今日の比喩

<br>

# レストランの注文

<br>

### 客（ブラウザ）が注文（Request）を出す
### 厨房（Server）が料理（Response）を返す

---

<!-- _class: no-header all-text-center align-center -->

# エラーコード = 店員のセリフ

<br>

<div class="highlight-box">
  <b>200：</b>「お待たせしました、ご注文の品です」<br><br>
  <b>404：</b>「申し訳ございません、<span class="red-accent-text">品切れです</span>」<br><br>
  <b>500：</b>「すみません、<span class="red-accent-text">厨房で火事です</span>」<br><br>
  <b>403：</b>「お客様、<span class="red-accent-text">会員限定メニューです</span>」
</div>

---

<!-- _class: no-header all-text-center align-center -->

# 今日の Copilot 機能

<br>

<div class="copilot-box">
  <b><code>/explain</code></b> — 選択したコードを解説させるコマンド<br><br>
  <b><code>#selection</code></b> — エディタで選択した範囲をCopilotに参照させる<br><br>
  コードを選んで聞けば、Copilotが解説してくれる
</div>

---

<!-- _class: no-header all-text-center align-center -->

# ハンズオン

<br>

<div class="experiment-box">
  <b>Part 1（5分）：レストランごっこ</b><br>
  Copilotに「私が客で、あなたが厨房です」と指示<br>
  404 を「品切れ」、500 を「厨房パンク」で再現<br><br>
  <b>Part 2（10分）：実際のHTTPを観察</b><br>
  ブラウザの DevTools（Networkタブ）でリクエスト・レスポンスを確認<br>
  ステータスコードを「レストランで言うと何？」と質問<br><br>
  <b>Part 3（5分）：/explain と #selection の初体験</b><br>
  HTMLの <code>&lt;form&gt;</code> タグや <code>fetch()</code> を選択<br>
  <b><code>#selection</code></b> → 「この選択範囲を説明して」
</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 3：役割分担 — Front / Back

---

<!-- _class: no-header all-text-center align-center -->

# 今日の比喩

<br>

# ホール係とシェフ

<br>

### ホール（見た目・接客） = フロントエンド
### シェフ（調理・素材加工） = バックエンド

---

<!-- _class: no-header all-text-center align-center -->

# 今日の Copilot 機能

<br>

<div class="copilot-box">
  <b><code>@workspace</code></b> — プロジェクト全体を見て回答してくれる<br><br>
  <b><code>#file:ファイル名</code></b> — 特定のファイルを指定して質問できる<br><br>
  「このプロジェクトの構造を教えて」が一発でできる
</div>

---

<!-- _class: no-header all-text-center align-center -->

# ハンズオン

<br>

<div class="experiment-box">
  <b>Part 1（5分）：見た目だけの電卓を作る</b><br>
  「HTML/CSSだけで電卓の見た目を作って。計算はできない状態で」<br>
  ボタンを押しても何も起きない → シェフがいない！<br><br>
  <b>Part 2（10分）：動く電卓にする + @workspace 体験</b><br>
  「JavaScriptで計算機能を追加して」→ 動く電卓になる<br>
  <b><code>@workspace</code></b> でフロント/バックの役割分担を質問<br>
  <b><code>#file:calculator.html</code></b> で特定ファイルを参照<br><br>
  <b>Part 3（5分）：境界線を引く</b><br>
  「ホールとシェフの境界線 ＝ API」という伏線を張る
</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 4：DBの概念 — CRUD操作

---

<!-- _class: no-header all-text-center align-center -->

# 今日の比喩

<br>

# 巨大冷蔵庫と在庫表

<br>

### 注文のたびに市場に行くわけじゃない
### 冷蔵庫（DB）から出す

---

<!-- _class: no-header all-text-center align-center table-center table-font-large -->

# CRUD = 冷蔵庫の4つの操作

<br>

| 操作 | 冷蔵庫 | DB | SNSなら |
|---|---|---|---|
| **C**reate | 食材を **買う** | データを作る | 投稿する |
| **R**ead | 中身を **見る** | データを読む | タイムライン表示 |
| **U**pdate | 数量を **変える** | データを更新 | プロフィール編集 |
| **D**elete | 腐ったものを **捨てる** | データを削除 | 投稿を削除 |

---

<!-- _class: no-header all-text-center align-center -->

# 今日の Copilot 機能

<br>

<div class="copilot-box">
  <b>Agent Mode</b> — Copilotが自律的にファイルを作成・編集してくれるモード<br><br>
  通常チャット：質問に答える<br>
  Agent Mode：<span class="green-accent-text">自律的に作業する</span><br><br>
  魔人に「大きな仕事」を任せられる
</div>

---

<!-- _class: no-header all-text-center align-center -->

# ハンズオン

<br>

<div class="experiment-box">
  <b>Part 1（5分）：CRUD を日常に置き換える</b><br>
  SNSの操作がCRUDのどれに対応するかCopilotに質問<br><br>
  <b>Part 2（12分）：Agent Mode で冷蔵庫アプリを作る</b><br>
  モードを <b>「Agent」</b> に切り替える<br>
  「冷蔵庫管理Webアプリを作って。CRUD操作ができるように」<br>
  Agent Modeが自律的にファイルを作る様子を<b>観察</b><br><br>
  <b>Part 3（3分）：Agent Mode の振り返り</b><br>
  「魔人に大きな仕事を任せた」感覚を言語化
</div>

---

<!-- _class: no-header all-text-center align-center -->

# どんな複雑なアプリも...

<br>

<div class="highlight-box">
  結局は <span class="green-accent-text">「データの読み書き」</span> しかしていない<br><br>
  SNSに「投稿する」= Create<br>
  タイムライン表示 = Read<br>
  プロフィール編集 = Update<br>
  投稿を削除する = Delete
</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 5：まとめ — Webの仕組み

---

<!-- _class: no-header all-text-center align-center -->

# 今日の比喩

<br>

# ピタゴラスイッチ

<br>

### すべての要素が連動して、一つの結果を生み出す

---

<!-- _class: no-header all-text-center align-center -->

# 「投稿」ボタンを押してからタイムラインに表示されるまで

<br>

<div class="highlight-box">
  1. <b>客</b>（ブラウザ）が「投稿」ボタンを押す<br><br>
  2. <b>ホール</b>（フロント）が注文票（Request）を厨房に渡す<br><br>
  3. <b>シェフ</b>（バックエンド）が冷蔵庫（DB）にデータを保存（Create）<br><br>
  4. <b>厨房</b>から「完了しました」（Response: 200）が返る<br><br>
  5. <b>ホール</b>がタイムラインに新しい投稿を表示（画面更新）
</div>

---

<!-- _class: no-header all-text-center align-center -->

# 今日の Copilot 機能

<br>

<div class="copilot-box">
  <b>Copilot Edits（Edit Mode）</b><br><br>
  既存のコードに対して「ここをこう変えて」と指示すると<br>
  <b>差分（diff）</b> として変更を提案してくれる<br><br>
  Accept / Reject で変更を取捨選択できる
</div>

---

<!-- _class: no-header all-text-center align-center -->

# ハンズオン

<br>

<div class="experiment-box">
  <b>Part 1（5分）：「投稿」の裏側をストーリーにする</b><br>
  レストランの比喩で処理フローを脚本にする<br><br>
  <b>Part 2（12分）：Edit Mode で既存コードを改造する</b><br>
  Day 4 の冷蔵庫アプリを開く<br>
  モードを <b>「Edit」</b> に切り替える<br>
  「食材ごとに賞味期限を追加して、期限切れは赤く表示して」<br>
  差分が提案される → Accept / Reject を練習<br><br>
  <b>Part 3（3分）：Week 1 の総復習</b><br>
  5つの比喩と5つのCopilot機能を振り返り
</div>

---

<!-- _class: no-header all-text-center align-center -->

# Week 1 Key Takeaways

<br>

### 1. **AIは「察してくれない」パートナー**
コンテキストが命。モデルの使い分けも重要

<br>

### 2. **HTTP通信 = レストランの注文**
`/explain` と `#selection` でコードを読み解ける

<br>

### 3. **フロント = ホール、バック = シェフ**
`@workspace` と `#file` でプロジェクト全体を見渡せる

<br>

### 4. **すべてのアプリは CRUD**
Agent Mode で大きな仕事を任せられる

---

<!-- _class: no-header all-text-center align-center -->

# 次回予告

<br>

# AI Paired Engineer #2
## プログラミングの概念 — 整理整頓とルール

<br>

### `#codebase`、`/fix`、`/tests`、Vision入力
### コード理解系の武器を手に入れます

---

<!-- _class: no-header all-text-center align-center -->

# **解散！！**
