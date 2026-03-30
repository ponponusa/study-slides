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

# AI Paired Engineer #3

## インフラと環境 — 家づくりと引っ越し

2026-03-30
ponpon.USA

---

<!-- _class: no-header all-text-center align-center -->

# 今週のテーマ

# インフラと環境

### PCの中だけでなく
### 世界中にコードが配備されるイメージを持つ

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

## Day 11：クラウド（IaaS / PaaS / SaaS）

---

<!-- _class: no-header all-text-center align-center -->

# 持ち家 vs 賃貸 vs ホテル

<div class="highlight-box">

**持ち家（IaaS）**= 全部自分で管理

**賃貸（PaaS）**= 建物は借りて、中は自分でしつらえる

**ホテル（SaaS）**= 全部おまかせ、部屋に入るだけ

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① クラウドの3層を理解する

<div class="experiment-box">

**【Copilot Chat → Ask モードで投げる】**

```
「IaaS・PaaS・SaaSの違いを、
 持ち家・賃貸・ホテルの比喩で説明して。
 それぞれ『自分が管理すること』と
 『サービスが管理すること』を表にまとめて。」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② AWSのサービスはどの層？

<div class="experiment-box">

**【続けて投げる】**

```
「AWS の EC2・S3・RDS・Lambda は、
 IaaS・PaaS・SaaS のどの層に近いか教えて。
 それぞれ何を自分で管理して、何をAWSが管理するか
 具体的に説明して。」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 11 気づきの言語化

<br>

<div class="highlight-box">

**「クラウドで『サーバーを借りる』は正確か？」**

→ 機能・能力を借りている。箱があるわけではない<br><br>

**問いかけ：** 自分が今使っているサービス（Slack、GitHub、AWS の EC2・Lambda・S3）はどの層？

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 12：コンテナ（Docker）

---

<!-- _class: no-header all-text-center align-center -->

# 家具付きカプセルホテル

<div class="highlight-box">

部屋ごとトラックで運べば、どこでも同じ環境で寝られる

**コンテナ = 環境ごと持ち運べる箱**

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① 「私の環境では動いた」問題

<div class="experiment-box">

**【Copilot Chat → Ask モードで投げる】**

```
「エンジニアがよく言う
 『私のPCでは動いたのに本番サーバーで動かない』
 という問題の具体的な事例を3つ挙げて。
 それぞれなぜ起きるのかも説明して。」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② Dockerで何が変わるか

<div class="experiment-box">

**【続けて投げる】**

```
「先ほどの3つの問題が、
 Dockerを使うとどのように解決されるか説明して。
 『環境をコンテナに閉じ込める』とはどういう意味かも。
 実際にDockerを動かさなくていいので、概念だけ教えて。」
```

</div>

<div class="observe-box">

- Dockerを使っていない → 「動作環境が人によって違う」
- Dockerを使っている → 「全員が同じ箱の中で動かす」

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 12 気づきの言語化

<br>

<div class="highlight-box">

**「『私の環境では動きました』がなぜ通用しないか」**

→ チームで開発するとき、全員の環境が微妙に違う<br><br>

**問いかけ：** コンテナが世界から消えたら、チーム開発で何が一番困る？

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 13：ログ・エラー（トラブルシューティング）

---

<!-- _class: no-header all-text-center align-center -->

# フライトレコーダー（日記）

<div class="highlight-box">

墜落原因を知るための唯一の手がかり

**ログがなければ、何が起きたか永遠にわからない**

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① 何も教えてくれないコードを作る

<div class="experiment-box">

**【Copilot Chat → Agent モードで投げる】**

```
「JavaScriptで以下の関数を作って。HTMLで動かせる形で。
 ファイル名: silent-error.html

 ・ユーザーが年齢を入力して送信すると処理する関数
 ・ただし、文字列・マイナス値・空入力が来ても
   エラーメッセージを一切表示しない不親切な実装にして
 ・不正な入力でも何事もなかったかのように処理を続けて」
```

**手順:** Live Server で開く → 文字列「abc」や「-5」を入力 → 何も起きない（Console も見る）

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② 詳細ログを出力するコードに変える

<div class="experiment-box">

**【続けて投げる（または #file で参照）】**

```
「silent-error.html の関数に、以下のログを追加して：
・関数が呼ばれたとき: 入力値を console.log で出力
・不正な入力（文字列・マイナス・空）を検出したとき:
  throw new Error(...) でエラーを投げて console.error で警告
・正常処理のとき: 結果を console.log で出力
さらに、エラー時はページ上にも赤字でメッセージを表示して」
```

**手順:** F12 → Console タブ → ログが流れる様子を観察

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 13 気づきの言語化

<br>

<div class="highlight-box">

**「エラーログは怖いものではなく、開発者への手紙」**<br><br>

**問いかけ：** ログが全くないシステムで障害が起きたら、あなたはどこから調査を始める？

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 14：API（連携）

---

<!-- _class: no-header all-text-center align-center -->

# コンセントとプラグ

<div class="highlight-box">

裏の発電所の仕組みを知らなくても、挿せば電気が来る

**API はサービス同士を繋ぐ「差し込み口」**

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① 郵便番号 → 住所が返ってくる魔法

<div class="experiment-box">

**【Copilot Chat → Agent モードで投げる】**

```
「郵便番号を入力するとAPIで住所を取得して表示する
 HTMLを作って。
 API: https://zipcloud.ibsnet.co.jp/api/search?zipcode=郵便番号
 （例: ?zipcode=1000001 で千代田区が返る）
 ・入力欄とボタンを配置
 ・ボタンを押すとfetch()でAPIを叩く
 ・住所（results[0].address1 / address2 / address3）を表示
 ・エラー時はメッセージを表示
 ファイル名: zipcode.html」
```

**手順:** Live Server で開く → 郵便番号を入力 → 住所が表示される体験

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② 何が起きているか観察する

<div class="experiment-box">

```
Step 1: ブラウザで F12 → Network タブを開く
Step 2: ボタンを押す → Network にリクエストが表示される
Step 3: リクエストをクリックして確認：
  ・URL（= どこに繋いだか）
  ・Status 200（= 電気が来た）
  ・Response（= 返ってきたデータ）

Step 4: Copilot Chat に聞く:
「このAPIのやり取りをコンセントとプラグの比喩で説明して。
 URLがプラグとしたら、Responseは何に当たる？」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 14 気づきの言語化

<br>

<div class="highlight-box">

**「自分で作らず、人の機能を使う賢さ」**

→ 郵便番号 DB を自分で作る必要はない → API で借りればいい<br><br>

**問いかけ：** 自分の日常で使っているアプリが、裏でどんな API を使っているか想像してみると？

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 15：まとめ（デプロイ）

---

<!-- _class: no-header all-text-center align-center -->

# 引っ越し大作戦

<div class="highlight-box">

自分のコード（家具）をコンテナ（トラック）に乗せて

クラウド（新居）に運んで

**世界中に公開する（開店パーティ）**

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験 リリースの旅路を脚本にする

<div class="experiment-box">

**【Copilot Chat → Ask モードで投げる】**

```
「ローカルPCで作ったWebアプリを、
 世界中の人がアクセスできる状態にするまでの流れを
 以下の登場人物を使って脚本（ナレーション形式）で書いて：

 登場人物:
 ・コード（家具）
 ・コンテナ（トラック）
 ・クラウドサーバー（新居）
 ・DNS（住所案内人）
 ・ブラウザ（訪問客）

 技術用語（Docker・デプロイ・API・クラウド）を
 台詞に自然に含めて」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Week 3 Key Takeaways

<div class="highlight-box">

- **クラウド** = 機能を借りる（IaaS / PaaS / SaaS）
- **コンテナ** = 環境ごと持ち運べる箱（「私の環境では」問題を解決）
- **ログ** = 開発者への手紙（怖くない、手がかり）
- **API** = コンセントとプラグ（仕組みを知らなくても使える）

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 次回予告

## AI Paired Engineer #4

### エンジニアの思考法 — プロの仕事術

技術的負債・ライブラリ・設計パターン・最終課題

---

<!-- _class: no-header all-text-center align-center -->

# **解散！！**
