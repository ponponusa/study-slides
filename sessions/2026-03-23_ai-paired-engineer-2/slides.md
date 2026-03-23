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

# AI Paired Engineer #2

## プログラミングの概念 — 整理整頓とルール

2026-03-23
ponpon.USA

---

<!-- _class: section -->
<!-- _paginate: false -->

## Week 2 のテーマ

---

<!-- _class: no-header all-text-center align-center -->

# Week 1 では「インターネットの地図」を手に入れた

<br>

### レストランの比喩で、通信の全体像を掴んだ

<br>

## Week 2 では

## **プログラムの中にある「ルール」を発見する**

---

<!-- _class: no-header all-text-center align-center -->

# Week 2 の狙い

<br>

<div class="highlight-box">
  プログラムの文法ではなく<br>
  <b>「なぜそのルールがあるのか」</b> という必然性を学ぶ<br><br>
  比喩の世界をCopilotに作らせ<br>
  コードの中に<span class="green-accent-text">「整理整頓のルール」</span>を発見する
</div>

---

<!-- _class: no-header all-text-center align-center -->

# 今週のテーマ

<br>

# プログラミングの概念

<br>

### 「整理整頓」と「ルール」

### すべては **ミスを防ぐ仕組み** だった

---

<!-- _class: no-header all-text-center align-center table-center table-font-large -->

# 今週の Copilot スキルツリー

<br>

| Day | テーマ | 習得する Copilot 機能 |
|---|---|---|
| **6** | 変数と型 | `#selection` + `/explain` |
| **7** | アルゴリズム | `/fix` |
| **8** | OOP | `#file` 複数指定 |
| **9** | テスト | Vision入力 |
| **10** | まとめ | Week 2 全機能の組み合わせ |

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 6：変数と型 — データ構造

---

<!-- _class: no-header all-text-center align-center -->

# 今日の比喩

<br>

# ラベル付き収納BOX

<br>

### 「靴下」の箱に「お茶」を入れると

### **朝パニックになる**

---

<!-- _class: no-header all-text-center align-center -->

# ラベル（型）は安全装置

<br>

<div class="highlight-box">
  引っ越しの荷造りで、<br>
  段ボールにラベルを貼らなかったらどうなるか？<br><br>
  <b>開けてみるまで中身がわからない</b><br><br>
  型（Type）は面倒なルールではなく<br>
  <span class="green-accent-text">ミスを防ぐ安全装置</span>
</div>

---

<!-- _class: no-header all-text-center align-center -->

# 今日の Copilot 機能

<br>

<div class="copilot-box">
  <b><code>#selection</code></b> — エディタで選択した範囲をCopilotに参照させる<br>
  「この部分について教えて」がピンポイントでできる<br><br>
  <b><code>/explain</code></b> — 選択したコードの解説を依頼するコマンド<br><br>
  組み合わせ: <code>#selection /explain このコードの問題を教えて</code>
</div>

---

<!-- _class: no-header all-text-center align-center -->

# ハンズオン

<br>

<div class="experiment-box">
  <b>Step 1（5分）：荷物管理アプリを作らせる</b><br>
  Agent Mode で「引っ越しの荷物管理Webアプリを作って。<br>
  段ボール箱にラベルと中身を登録して一覧表示」<br>
  LiveServer でプレビュー<br><br>
  <b>Step 2（5分）：意図的に型の混乱を起こす</b><br>
  個数フィールドの足し算を文字列のまま実行<br>
  <code>"3" + 2</code> → <code>"32"</code> になるバグを体験！<br><br>
  <b>Step 3（7分）：<code>#selection</code> + <code>/explain</code> で原因調査</b><br>
  バグのある行を選択 →<br>
  <code>#selection /explain このコードの問題を教えて</code><br>
  「ラベルが違うものを混ぜたから壊れた」ことを確認
</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 6 の気づき

<br>

<div class="highlight-box">
  型が合わないと<span class="red-accent-text">意図しない動作</span>になる<br>
  ＝ ラベルのない箱を開けたら中身が違った<br><br>
  <b><code>#selection</code></b> でピンポイントに質問できる<br><br>
  型は「面倒なルール」ではなく<b>「安全装置」</b>
</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 7：アルゴリズム — 分岐と反復

---

<!-- _class: no-header all-text-center align-center -->

# 今日の比喩

<br>

# 自動販売機の裏側

<br>

### お金を入れる → 金額を判定 → 足りなければ返却

### 足りれば商品排出 → お釣り計算

---

<!-- _class: no-header all-text-center align-center -->

# プログラミング = 手順書を書くこと

<br>

<div class="highlight-box">
  自販機は「手順書」通りに動いている<br><br>
  <b>「もし〜なら」（分岐 = if）</b><br>
  <b>「〜を繰り返す」（反復 = for/while）</b><br><br>
  この2つがあれば<br>
  <span class="green-accent-text">ほとんどの手順を表現できる</span>
</div>

---

<!-- _class: no-header all-text-center align-center -->

# 今日の Copilot 機能

<br>

<div class="copilot-box">
  <b><code>/fix</code></b> — バグを自動修正するスラッシュコマンド<br><br>
  エラーが出ているコードを選択して<br>
  <code>/fix</code> と打つだけで修正案を提示してくれる<br><br>
  「壊れた自販機を直す」道具
</div>

---

<!-- _class: no-header all-text-center align-center -->

# ハンズオン（事前準備あり）

<br>

<div class="highlight-box">
  メンターが <b>「バグ入り自販機アプリ」</b> を用意しています<br><br>
  バグ1: 存在しない商品（ジュース）のボタンがある<br>
  バグ2: 投入金額が文字列のまま比較されている<br>
  バグ3: <code>></code> であるべき箇所が <code>>=</code> になっていない
</div>

---

<!-- _class: no-header all-text-center align-center -->

# ハンズオン

<br>

<div class="experiment-box">
  <b>Step 1（3分）：バグ入り自販機を動かす</b><br>
  LiveServer で開いて操作してみる<br>
  「150円入れたのにコーラが買えない！」<br><br>
  <b>Step 2（7分）：<code>/fix</code> でバグを直す</b><br>
  バグのある行を選択 → <code>/fix</code><br>
  存在チェック追加 → <code>>=</code> に修正 → 文字列を数値変換<br>
  各修正を Accept → LiveServer で再確認<br><br>
  <b>Step 3（7分）：分岐と反復を発見する</b><br>
  修正後のコードで「if と for をすべて見つけて<br>
  自販機の動作に例えて説明して」とCopilotに質問
</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 7 の気づき

<br>

<div class="highlight-box">
  プログラミングは <span class="green-accent-text">「手順の言語化」</span> に過ぎない<br><br>
  <b><code>/fix</code></b> がエラーの原因を推測し、<br>
  適切な修正を提案してくれる<br><br>
  分岐（if）と反復（for）で<b>ほとんどの処理が表現できる</b>
</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 8：OOP — オブジェクト指向

---

<!-- _class: no-header all-text-center align-center -->

# 今日の比喩

<br>

# RPGのジョブシステム

<br>

### 「戦士」という設計図（クラス）から

### 「勇者アレク」「戦士タロウ」という個体を作る

---

<!-- _class: no-header all-text-center align-center -->

# 設計図（クラス）は共通、実体は個別

<br>

<div class="highlight-box">
  スライムもドラゴンも<br>
  「攻撃する」「ダメージを受ける」という<b>共通の行動</b>を持っている<br><br>
  でも攻撃力やHPは<b>違う</b><br><br>
  <span class="green-accent-text">設計図（クラス）は共通、実体（インスタンス）は個別</span><br>
  これがオブジェクト指向の核心
</div>

---

<!-- _class: no-header all-text-center align-center -->

# 今日の Copilot 機能

<br>

<div class="copilot-box">
  <b><code>#file</code> 複数指定</b><br><br>
  <code>#file:warrior.js #file:mage.js</code><br>
  <code>このファイル同士の関係を教えて</code><br><br>
  複数ファイルを同時に参照させて<br>
  <b>ファイル間の関係</b>を横断的に質問できる
</div>

---

<!-- _class: no-header all-text-center align-center -->

# ハンズオン

<br>

<div class="experiment-box">
  <b>Step 1（6分）：RPGキャラ管理を作らせる</b><br>
  Agent Mode で「RPGキャラ管理システムを作って。<br>
  <code>character.js</code>に基底クラス、<code>warrior.js</code>に戦士、<br>
  <code>mage.js</code>に魔法使い、<code>battle.html</code>にバトル画面」<br><br>
  <b>Step 2（5分）：<code>#file</code> で関係性を質問</b><br>
  <code>#file:character.js #file:warrior.js</code><br>
  「戦士は基底クラスの何を継承していますか？」<br>
  <code>#file:warrior.js #file:mage.js</code><br>
  「この2つの共通点と違いを教えて」<br><br>
  <b>Step 3（6分）：新しい職業を追加する</b><br>
  Agent Mode で「<code>healer.js</code> にヒーラーを追加して。<br>
  heal メソッド付きで」→ 設計図のルールに従えば増やせる！
</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 8 の気づき

<br>

<div class="highlight-box">
  <b>クラス（設計図）</b>と<b>インスタンス（実体）</b>の関係<br><br>
  継承により共通の機能が<span class="green-accent-text">自動的に引き継がれる</span><br><br>
  <b><code>#file</code> の複数指定</b>で<br>
  ファイル間の関係を横断的に質問できる
</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 9：テスト — 品質保証

---

<!-- _class: no-header all-text-center align-center -->

# 今日の比喩

<br>

# 料理の味見（毒見）

<br>

### どんなに腕の良いシェフでも

### **味見なしで料理を出すことはない**

---

<!-- _class: no-header all-text-center align-center -->

# テストコード = 自動味見マシン

<br>

<div class="highlight-box">
  客に出す前に、必ずスプーンで一口味見する<br><br>
  テストコードとは<b>「自動味見マシン」</b>のこと<br><br>
  一度設定すれば<br>
  <span class="green-accent-text">何度でも同じ基準で味見してくれる</span>
</div>

---

<!-- _class: no-header all-text-center align-center -->

# 今日の Copilot 機能

<br>

<div class="copilot-box">
  <b>Vision入力</b> — チャットに画像を添付して質問できる<br><br>
  スクリーンショット、UI、エラー画面など<br>
  <b>「この画面のバグを見つけて」</b> ができる<br><br>
  ドラッグ&ドロップ or クリップアイコンで添付
</div>

---

<!-- _class: no-header all-text-center align-center -->

# ハンズオン（事前準備あり）

<br>

<div class="highlight-box">
  メンターが <b>「バグ入り計算機アプリ」</b> を用意しています<br><br>
  意図的なバグ: 割り算で小数点以下が切り捨てられる<br>
  例: <code>10 ÷ 3 = 3</code>（正しくは <code>3.333...</code>）
</div>

---

<!-- _class: no-header all-text-center align-center -->

# ハンズオン

<br>

<div class="experiment-box">
  <b>Step 1（4分）：バグを見つける</b><br>
  計算機をブラウザで操作し、バグを発見<br>
  「10 ÷ 3 = 3」→ おかしい！<br>
  バグが映った画面のスクリーンショットを撮る<br><br>
  <b>Step 2（6分）：Vision入力でバグを報告</b><br>
  スクショを Copilot Chat にドラッグ&ドロップ<br>
  「この計算結果がおかしい。原因を特定して修正案を教えて」<br>
  Copilot が画像を解析する様子を観察<br><br>
  <b>Step 3（7分）：テストコードを書かせる</b><br>
  「割り算のテストコードを書いて。<br>
  正常系・小数点・ゼロ除算をカバーして」<br>
  テスト実行 → バグが自動検出されることを確認
</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 9 の気づき

<br>

<div class="highlight-box">
  <b>Vision入力</b>でスクショからバグを特定できる<br><br>
  テストコードは<span class="green-accent-text">「一度書けば何度でも確認してくれる」</span><br>
  安心装置<br><br>
  テストコード ＝ <b>安心料</b>
</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 10：まとめ — 身近なプログラム

---

<!-- _class: no-header all-text-center align-center -->

# 今日の比喩

<br>

# コンビニレジの裏側

<br>

### 毎日使うレジに Week 2 の全概念が詰まっている

---

<!-- _class: no-header all-text-center align-center -->

# コンビニレジ = プログラムの概念の集合体

<br>

<div class="highlight-box">
  <b>変数</b> — 商品名・価格・合計金額<br><br>
  <b>分岐（if）</b> — 年齢確認（酒・タバコ）<br><br>
  <b>反復（for）</b> — バーコードスキャンの繰り返し<br><br>
  <b>クラス</b> — 商品カテゴリ（食品・飲料・日用品）<br><br>
  <b>テスト</b> — レシート確認（合計が合っているか）
</div>

---

<!-- _class: no-header all-text-center align-center -->

# 今日の Copilot 機能

<br>

<div class="copilot-box">
  <b>Week 2 の全機能を組み合わせて使う</b><br><br>
  <code>#selection</code>、<code>/explain</code>、<code>/fix</code>、<code>#file</code>、Vision入力<br><br>
  状況に応じて<span class="green-accent-text">使い分ける</span>実践
</div>

---

<!-- _class: no-header all-text-center align-center -->

# ハンズオン

<br>

<div class="experiment-box">
  <b>Step 1（3分）：コンビニレジの仕様を設計する</b><br>
  Ask Mode で「コンビニレジの処理フローを設計して。<br>
  バーコードスキャン・年齢確認・合計計算・お釣り・レシート」<br><br>
  <b>Step 2（8分）：Agent Mode で実装させる</b><br>
  「設計に基づいてレジシミュレーターを作って。<br>
  商品クラス・レジクラス・年齢確認の分岐・<br>
  スキャンのループを含めて。HTML/CSS/JSで完結」<br>
  Week 2 の概念が全部登場することを確認<br><br>
  <b>Step 3（6分）：バグ修正とテスト追加</b><br>
  「消費税計算が抜けている」等を <code>/fix</code> で修正<br>
  「合計金額計算のテストを書いて」で自動テスト追加
</div>

---

<!-- _class: no-header all-text-center align-center -->

# 現実世界がプログラムに見え始める

<br>

<div class="highlight-box">
  コンビニレジ、自販機、電車の改札、エレベーター...<br><br>
  どれも <span class="green-accent-text">変数・分岐・反復・クラス</span> で動いている<br><br>
  Week 2 で学んだ「整理整頓のルール」は<br>
  <b>すべての機械の中にある</b>
</div>

---

<!-- _class: no-header all-text-center align-center table-center table-font-large -->

# Week 2 Key Takeaways

<br>

| 比喩 | IT概念 | Copilot機能 |
|---|---|---|
| ラベル付き収納BOX | 変数と型 | `#selection` + `/explain` |
| 自動販売機の裏側 | アルゴリズム | `/fix` |
| RPGのジョブシステム | OOP | `#file` 複数指定 |
| 料理の味見 | テスト | Vision入力 |
| コンビニレジ | 全概念統合 | 全機能組み合わせ |

---

<!-- _class: no-header all-text-center align-center -->

# 次回予告

<br>

# AI Paired Engineer #3

## インフラと環境 — 家づくりと引っ越し

<br>

### `@workspace`、`#codebase`、`/tests`、Agent Mode応用

### インフラ系の武器を手に入れます

---

<!-- _class: no-header all-text-center align-center -->

# **解散！！**
