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
  .observe-box {
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

<!-- _class: no-header all-text-center align-center -->

# 今週のテーマ

# プログラミングの概念

### プログラムの「文法」ではなく
### 「なぜそのルールがあるのか」という必然性を学ぶ

---

<!-- _class: no-header all-text-center align-center table-center table-font-large -->

# 事前準備の確認

| 確認項目 | 手順 |
| -------- | ---- |
| **GitHub Copilot** | 拡張機能タブで有効化されているか確認 |
| **GitHub Copilot Chat** | サイドバーの Copilot アイコン → Chat パネルが開くか確認 |
| **Live Server** | 拡張機能タブで有効化されているか確認 |

<div class="highlight-box">

HTML ファイルを右クリック →「Open with Live Server」

または右下ステータスバーの「Go Live」をクリック

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 6：変数と型

---

<!-- _class: no-header all-text-center align-center -->

# 「ラベル付き収納 BOX」

<br>

### 「靴下」の箱に「お茶」を入れると朝パニックになる

### 型はラベル = <span class="red-accent-text">間違いを防ぐ仕組み</span>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① 型を壊してみる

<br>

<div class="experiment-box">

**【Copilot Chat → Agent モードで投げる】**

```
「JavaScriptで以下の2つを計算するHTMLを作って：
1. 数字の 1 + 数字の 2
2. 文字列の "1" + 数字の 2
両方の結果をページに表示して。ファイル名: type-test.html」
```

手順: Live Server で開く → 結果を確認

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 何が起きた？

<br>

<div class="observe-box">

- 「1 + 2 = 3」なのに「"1" + 2 = "12"」になる

- なぜ？ → <span class="red-accent-text">型が違うから足し算の意味が変わる</span>

- 数値の `+` は「足し算」 / 文字列の `+` は「くっつける」

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② /explain で解説させる

<br>

<div class="experiment-box">

**【JSのコード部分（数値と文字列の計算部分）を選択して】**

```
Copilot Chat で: /explain
「この結果の違いが起きる理由を、
 プログラム初心者にわかるように説明して」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 6 の気づき

<br>

<div class="highlight-box">

型（Type）は面倒なルールではなく、<span class="green-accent-text">ミスを防ぐ安全装置</span><br><br>

**問いかけ：** 型のない世界では何が困る？<br><br>

→ 銀行システムで「金額」に文字列が入ったら...

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 7：アルゴリズム

---

<!-- _class: no-header all-text-center align-center -->

# 「電車の乗り換え案内」

<br>

### 「もし遅延なら（if）別のルートを選ぶ」

### 「全駅に停車する（loop）」

### プログラムは<span class="blue-accent-text">条件と繰り返しの組み合わせ</span>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① 朝のルーティンをコードにする

<br>

<div class="experiment-box">

まず自分で「起きてから家を出るまで」を箇条書きにする（3分）

<br>

**【Copilot Chat → Ask モードで投げる】**

```
「以下の朝のルーティンを、if文とループを使った
擬似コード（日本語）に翻訳して。
"雨が降っていたら傘を持つ" の分岐も含めて。

[自分の箇条書きをここに貼る]」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② 擬似コードを動くコードにする

<br>

<div class="experiment-box">

**【Chat モードを Agent に切り替えて投げる】**

```
「上の擬似コードを、ブラウザで動くJavaScriptに変換して。
条件分岐（if）とループ（for/while）を実際のJS構文で書いて。
HTML1ファイルで完結する形で。ファイル名: routine.html」
```

<br>

→ Agent モードがファイルを自動作成 → Live Server で開いて動作確認<br>
観察: どの行が if？ どの行が loop？

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 7 の気づき

<br>

<div class="highlight-box">

「プログラミングとは<span class="green-accent-text">『手順と条件』の言語化</span>に過ぎない」<br><br>

**問いかけ：** 今日やったこと以外で、<br>
ループしている日常の作業を1つ挙げるとしたら？

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 8：OOP（オブジェクト指向）

---

<!-- _class: no-header all-text-center align-center -->

# 「RPGの職業とキャラ」

<br>

### 「戦士」という設計図（クラス）から

### 「Aさん」「Bさん」（インスタンス）を作る

### <span class="blue-accent-text">設計図と実体は別物</span>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① ドラクエのモンスターをクラスで表現

<br>

<div class="experiment-box">

**【Copilot Chat → Agent モードで投げる】**

```
「ドラゴンクエストのモンスターをJavaScriptのclassで表現して。
モンスターには名前・HP・攻撃力を持たせて、
attack() というメソッドで攻撃できるようにして。
スライム・ドラゴン・ゴーレムの3種類を作って、
それぞれに attack() を呼んだ結果も表示して。
HTML1ファイルで。ファイル名: monsters.html」
```

→ Agent がファイルを作成 → Live Server で開いて動作確認

観察: スライムもドラゴンも同じ `attack()` メソッドを持っている

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② #selection でクラスを解剖する

<br>

<div class="experiment-box">

```
Step 1: monsters.html をエディタで開く

Step 2: 「class Monster { ... }」の部分をマウスで選択

Step 3: Copilot Chat（Ask モード）で:
「#selection これがクラス（設計図）です。
 このクラスから作られた slime や dragon が
 インスタンス（実体）です。
 設計図と実体の違いを料理に例えて説明して」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 8 の気づき

<br>

<div class="highlight-box">

クラス（設計図）= レシピ / インスタンス（実体）= 実際に作った料理<br><br>

**問いかけ：** クラスとインスタンスを<br>
料理以外で例えるとしたら？

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 9：テスト

---

<!-- _class: no-header all-text-center align-center -->

# 「料理の毒見」

<br>

### 客に出す前に必ずスプーンで一口味見する

### テストコードは<span class="red-accent-text">「自動毒見ロボット」</span>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① バグのある電卓を作る

<br>

<div class="experiment-box">

**【Copilot Chat → Agent モードで投げる】**

```
「JavaScriptで電卓を作って。ただし、
わざと以下のバグを仕込んで：
・5 + 3 を計算すると正しく 8 が返る
・10 ÷ 2 を計算すると間違えて 6 が返る
・それ以外は正常に動く
バグがあることは見た目ではわからない状態にして。
HTML1ファイルで。ファイル名: buggy-calc.html」
```

<br>

観察: 普通に使っても気づかない → でも確実にバグがある

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② /tests でバグを自動発見する

<br>

<div class="experiment-box">

```
Step 1: 生成されたJSの計算ロジック部分（calculate 関数など）を選択

Step 2: Copilot Chat（Ask モード）で /tests を実行:
/tests

Step 3: テスト生成後、Agent モードに切り替えて続けて投げる:
「ブラウザで動くassert形式に変えて。
 期待値と実際の値を比較して、
 NG は赤・OK は緑でページに表示して。
 ファイル名: buggy-calc-test.html」

→ Agent モードがファイルを自動生成する

Step 4: Live Server で開く → 10÷2 の行が赤くなることを確認
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 自動で見つかった

<br>

<div class="observe-box">

- バグを「探した」のではなく「自動的に見つかった」

- これが「テストコード = <span class="green-accent-text">自動毒見ロボット</span>」の意味

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 9 の気づき

<br>

<div class="highlight-box">

**「テストコードが世界から消えたら何が困る？」**<br><br>

→ バグが本番まで気づかれない<br>
→ リリースのたびに人間が全部確認する必要がある<br><br>

テストコードは<span class="green-accent-text">「安心料」</span>

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 10：まとめ

---

<!-- _class: no-header all-text-center align-center -->

# 「自動販売機の裏側」

<br>

### お金を入れる → ランプ点灯 → ボタン押下 → 排出 → お釣り

### これも<span class="blue-accent-text">変数・if・ループ</span>でできている

---

<!-- _class: no-header all-text-center align-center -->

# 実験 自販機をプログラムで設計する

<br>

<div class="experiment-box">

**【Copilot Chat → Ask モードで投げる】**

```
「自動販売機の動作を、以下の用語を使って説明して：
・変数（お金の合計、選ばれた商品、在庫数）
・if文（お金が足りるか、在庫があるか）
・ループ（複数の商品ボタンを確認する処理）
プログラムを書かず、日本語の説明だけで。」

→ 続けて:
「この説明を、小学生にわかるように言い直して」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Week 2 Key Takeaways

<br>

### 1. **変数と型 = ラベル付き収納BOX**

型はミスを防ぐ安全装置

### 2. **アルゴリズム = 条件（if）と繰り返し（loop）の組み合わせ**

手順と条件を言語化するだけ

### 3. **クラスとインスタンス = レシピと実際の料理**

設計図と実体は別物

### 4. **テスト = 自動毒見ロボット**

バグを自動発見する仕組み

---

<!-- _class: no-header all-text-center align-center -->

# 次回予告

<br>

# AI Paired Engineer #3

## インフラと環境 — 家づくりと引っ越し

<br>

### クラウド・Docker・ログ・APIの世界へ

---

<!-- _class: no-header all-text-center align-center -->

# **解散！！**
