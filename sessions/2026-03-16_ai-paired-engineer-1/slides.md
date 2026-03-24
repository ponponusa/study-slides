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

# AI Paired Engineer #1

## インターネットの世界観 — レストランと手紙

2026-03-16
ponpon.USA

---

<!-- _class: no-header all-text-center align-center -->

# 今週のテーマ

# インターネットの世界観

### 目に見えない通信のやり取りを
### 物理的なモノの移動として脳内変換させる

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

## Day 1：プロンプトの基礎

---

<!-- _class: no-header all-text-center align-center -->

# 魔法のランプの魔人

<div class="highlight-box">

曖昧なお願いは変な叶え方をする

**「3つ願いを叶えてやろう」→「お金持ちになりたい」→ 銀行強盗をさせられた**

**プロンプト = 魔人への正確な指示書**

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① 曖昧な指示 vs 具体的な指示

<div class="experiment-box">

**【Copilot Chat → Ask モードで投げる】**

```
①「カレーの作り方を教えて」

②「一人暮らしの男性が自宅で、
   市販のルーを使って15分以内に作れる
   カレーのレシピを教えて。
   材料は近所のコンビニで揃うものだけで。」
```

**観察：** 回答の具体さ・使いやすさの違いを比較する

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② 自分のプロンプトを改善する

<div class="experiment-box">

**【続けて Ask モードで投げる】**

```
「私はこんな質問をよくAIに投げています：
 [自分が過去に投げた質問を1つ書く]

 この質問をより具体的で答えやすいプロンプトに
 書き直してください。
 改善した理由も教えてください。」
```

**観察：** Copilot が追加した「条件・制約・背景」を確認する

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 1 の気づき

<br>

<div class="highlight-box">

「AIは察してくれない」— 人間なら文脈を読むが、AIは書いてあることしか処理しない<br><br>

**問いかけ：** 「AIは察してくれない」を自分の言葉で一言にするとしたら？

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 2：HTTP 通信（Client / Server）

---

<!-- _class: no-header all-text-center align-center -->

# レストランの注文票

<div class="highlight-box">

**客（ブラウザ）** → 注文票（Request）→ **厨房（Server）** → 料理（Response）

注文が通らないときは理由（ステータスコード）がある

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① レストランごっこ

<div class="experiment-box">

**【Copilot Chat → Ask モードで投げる】**

```
「あなたはレストランの厨房（Webサーバー）です。
 私はお客（ブラウザ）として注文を出します。
 以下のHTTPステータスコードを、
 レストランのシーンとしてセリフで再現してください：
 ・200 OK（注文が通った）
 ・404 Not Found（そのメニューは存在しない）
 ・500 Internal Server Error（厨房で火事が起きた）
 ・403 Forbidden（VIP客だけの特別メニューを頼まれた）」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② 本物の HTTP 通信を観察する

<div class="experiment-box">

**【Copilot Chat → Agent モードで投げる】**

```
「jsonplaceholder.typicode.com の /todos/1 に
 fetch() でアクセスして、結果をページに表示する
 HTMLを作って。ファイル名: http-demo.html」
```

**手順:** Live Server で開く → F12 → Network タブを確認

- URL（= どこに繋いだか）
- Status 200（= 料理が届いた）
- Response（= 返ってきたデータ）

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 2 の気づき

<br>

<div class="highlight-box">

「HTTPステータスコード」は怖い数字ではなく、<span class="green-accent-text">厨房からのメッセージ</span><br><br>

**問いかけ：** 404 を見たとき、次から何を確認するか？一言で。

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 3：役割分担（Front / Back）

---

<!-- _class: no-header all-text-center align-center -->

# ホール係とシェフ

<div class="highlight-box">

**ホール係（フロントエンド）** = 見た目・接客・お客との窓口

**シェフ（バックエンド）** = 調理・加工・データの処理

どちらが欠けても、客に料理は届かない

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① ホール係だけの電卓を作る

<div class="experiment-box">

**【Copilot Chat → Agent モードで投げる】**

```
「見た目だけの電卓HTMLを作って。
 ・数字ボタン、+−×÷ボタン、=ボタンを並べる
 ・ただし、JavaScriptは一切書かない
 ・ボタンを押しても何も起きない、デザインだけの電卓で
 ファイル名: calc-nojs.html」
```

**手順:** Live Server で開く → ボタンを押す → 何も起きない

→ これが「ホール係しかいないレストラン」

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② シェフを雇う（JS を追加）

<div class="experiment-box">

**【続けて Agent モードで投げる】**

```
「calc-nojs.html にJavaScriptを追加して、
 実際に計算できる電卓にして。
 ファイル名: calc-with-js.html」
```

**手順:** ファイルが生成されたら JS の計算ロジック部分を選択

```
Copilot Chat（Ask モード）で #selection を使って:
「#selection これがバックエンド相当のロジックです。
 ホール係（HTML）とシェフ（JS）の
 役割分担を説明して」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 3 の気づき

<br>

<div class="highlight-box">

「フロントとバック」は技術の話ではなく、<span class="blue-accent-text">役割の分担</span><br><br>

**問いかけ：** この電卓を「SNS のいいね機能」にするには何が必要か？ → なぜバックエンドが必要になるのか自分で答えてみる

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 4：DB の概念（CRUD 操作）

---

<!-- _class: no-header all-text-center align-center -->

# 巨大な冷蔵庫

<div class="highlight-box">

データベース = **世界最大の冷蔵庫**

「買う（Create）・見る（Read）・変える（Update）・捨てる（Delete）」

どんなアプリも、データに対してこの **4つ** しかしていない

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① Instagram を CRUD で分解する

<div class="experiment-box">

**【Copilot Chat → Ask モードで投げる】**

```
「Instagramの機能を、CRUD（Create / Read / Update / Delete）で
 分解した表を作って。
 ・ユーザーがする操作
 ・それがCRUDのどれに当たるか
 ・裏でデータベースに何が起きているか
 の3列で。」
```

**観察：** 「写真を投稿する」「いいねする」「プロフィールを編集する」「投稿を削除する」がどの操作に対応するか確認する

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② 冷蔵庫アプリを自律生成する

<div class="experiment-box">

**【Copilot Chat → Agent モードで投げる】**

```
「食材を管理する冷蔵庫アプリのHTMLを作って。
 ・食材の追加（Create）
 ・食材一覧の表示（Read）
 ・食材名の編集（Update）
 ・食材の削除（Delete）
 の4機能を実装して。
 データはlocalStorageに保存して、
 ページを再読み込みしても消えないようにして。
 ファイル名: fridge.html」
```

**手順:** Live Server で開く → CRUD を全部試す → リロードしてデータが残ることを確認

</div>

<div class="observe-box">

- Instagram と同じ CRUD をしている → スケールと扱うデータが違うだけ

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 4 の気づき

<br>

<div class="highlight-box">

「この冷蔵庫アプリと Instagram の本質的な違いは何か」<br><br>

**問いかけ：** CRUD の構造は同じ。スケールと扱うデータが違うだけ。あなたが使っているアプリを 1 つ CRUD で分解すると？

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 5：まとめ（Web の仕組み）

---

<!-- _class: no-header all-text-center align-center -->

# ピタゴラスイッチ

<div class="highlight-box">

すべての要素が連動している

**ブラウザ → HTTP → サーバー → DB → API → レスポンス → 画面**

1つが欠けると、ボールは転がらない

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① いいねボタンの旅路を脚本にする

<div class="experiment-box">

**【Copilot Chat → Ask モードで投げる】**

```
「Instagramで『いいね』ボタンを押してから
 ハートが赤くなるまでの流れを、
 以下の登場人物を使って脚本（ナレーション形式）で書いて：

 登場人物:
 ・ブラウザ（お客）
 ・HTTPリクエスト（注文票）
 ・Webサーバー（ホール係）
 ・データベース（冷蔵庫）
 ・HTTPレスポンス（料理）

 技術用語（HTTP・CRUD・API・JSON）を
 台詞に自然に含めて」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② 冷蔵庫アプリに機能追加する

<div class="experiment-box">

**【Copilot Chat → Agent モードで投げる】**

```
「fridge.html に、食材の賞味期限を登録・表示する機能を追加して。
 期限が3日以内の食材は赤字で表示して。」
```

**観察：** Agent モードが提案する diff（変更箇所）を確認する

- どのファイルの何行目が変わるか
- Accept / Discard で変更を選択する体験

</div>

<div class="observe-box">

- 既存コードを「壊さずに」機能追加できた → これがチーム開発の基本

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 5 の気づき

<br>

<div class="highlight-box">

Week 1 で登場した全員が繋がっていた<br><br>

**問いかけ：** 今日の旅路を、スマホを使ったことのない祖父母に説明するとしたら？

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Week 1 Key Takeaways

<div class="highlight-box">

- **プロンプト** = 魔人への正確な指示書（曖昧さをなくす）
- **HTTP 通信** = レストランの注文票と料理（Request / Response）
- **Front / Back** = ホール係とシェフ（役割の分担）
- **CRUD** = 冷蔵庫の 4 操作（どんなアプリも同じ）

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 次回予告

## AI Paired Engineer #2

### プログラミングの概念 — 整理整頓とルール

変数・型・アルゴリズム・OOP・テスト

---

<!-- _class: no-header all-text-center align-center -->

# **解散！！**
