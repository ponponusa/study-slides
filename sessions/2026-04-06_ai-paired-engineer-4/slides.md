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

# AI Paired Engineer #4

## エンジニアの思考法 — プロの仕事術

2026-04-06
ponpon.USA

---

<!-- _class: no-header all-text-center align-center -->

# 今週のテーマ

# エンジニアの思考法

### 技術を手段として使い
### ビジネスに貢献する判断力を養う

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

## Day 16：技術的負債（保守性）

---

<!-- _class: no-header all-text-center align-center -->

# 散らかった部屋のツケ

<div class="highlight-box">

「とりあえず床に置く」を続けると、掃除業者の費用が高くなる

**技術的負債 = 後で払うことになるコストの蓄積**

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① 「動けばいい」コードを作る

<div class="experiment-box">

**【Copilot Chat → Agent モードで投げる】**

```
「足し算・引き算・掛け算ができるHTMLを作って。
 ただし、わざと以下のように書いて：
 ・同じ処理をコピペして3回書く（関数化しない）
 ・変数名は a, b, c, x, y, z などを使う
 ・コメントは一切書かない
 動けばいい、を優先した実装で。
 ファイル名: messy-calc.html」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② 機能追加を頼んでみる

<div class="experiment-box">

**【Agent モードで続けて投げる】**

```
「messy-calc.html に割り算機能を追加して。
 さらに、計算結果を履歴として下に追記する機能も追加して。」

→ Copilot の応答と変更範囲を観察する
  ・どれだけの行数が変更されたか
  ・Copilot 自身が苦戦していないか
```

</div>

<div class="observe-box">

- 整理されたコードなら3行の変更で済むはずが...
- 「散らかった部屋に家具を追加する」のは大変

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 16 気づきの言語化

<br>

<div class="highlight-box">

「動けばいい」はプロの仕事ではない<br><br>

**問いかけ：** 「技術的負債が積み重なった場合、誰が損をする？」

→ 未来の自分、チームメンバー、会社（開発スピードの低下）

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 17：ライブラリ（車輪の再発明）

---

<!-- _class: no-header all-text-center align-center -->

# レトルトと手料理

<div class="highlight-box">

カレーをスパイスから調合する（全部自作）か、ルーを使うか（ライブラリ）

**プロは「価値を届けること」を優先する**

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① カレンダーを自作するとどうなる？

<div class="experiment-box">

**【Copilot Chat → Ask モードで投げる】**

```
「Webページにカレンダー機能（月表示、日付選択、
 前月・次月への移動）をゼロから実装するとしたら、
 どれくらいの工数（時間）がかかる？
 考慮すべき実装項目を全部列挙してから見積もって。」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② ライブラリなら何行？

<div class="experiment-box">

**【Agent モードで投げる】**

```
「flatpickr というカレンダーライブラリを使って、
 日付選択ができるシンプルなHTMLを作って。
 CDNから読み込む形で、インストール不要で。
 ファイル名: calendar.html」

→ 生成されたコード量を自作の見積もりと比較する
```

</div>

<div class="observe-box">

- 自作: 数十時間 + バグ対応 + テスト
- ライブラリ: 数行 + CDN読み込みのみ
- 「価値を届ける」= カレンダーを作ることではなく、カレンダーを使って何をするか

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 17 気づきの言語化

<br>

<div class="highlight-box">

「作る」ことへの固執を捨て、「価値を届ける」ことを優先する<br><br>

**問いかけ：** 「ライブラリを使わないことが正解になるのはどんな場合？」

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 18：設計パターン（Design Pattern）

---

<!-- _class: no-header all-text-center align-center -->

# 将棋の「定跡」

<div class="highlight-box">

先人が編み出した「こう指せば勝てる」型

**設計パターン = 先人が編み出した「こう設計すれば問題が解ける」型**

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① Observer パターンを理解する

<div class="experiment-box">

**【Copilot Chat → Ask モードで投げる】**

```
「Observer パターンを、新聞配達の仕組みに例えて説明して。
 ・新聞社（Subject）
 ・購読者（Observer）
 ・購読・解約・配達の仕組み
 を使って、パターンの意図と使い所を教えて。
 その後、JavaScriptでシンプルな実装例も見せて。」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② Plan モードで設計計画を作る

<div class="experiment-box">

**【Copilot Chat → Plan モードに切り替えて投げる】**

```
「Observer パターンを使って、
 ボタンを押すと複数のUIパーツが一斉に更新される
 シンプルなHTMLアプリの実装計画を作って。
 コードは書かず、計画だけ先に出して。」

→ Plan モードが実装ステップを先に提示する体験
→ 計画を確認してから「実行」するプロセスを観察
```

</div>

<div class="observe-box">

- Plan モード = 「設計図を先に引いてから工事を始める」
- コードを書き始める前に、何を作るかが明確になる

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 18 気づきの言語化

<br>

<div class="highlight-box">

「難しそうな用語も、実は日常の仕組みと同じ」<br><br>

**問いかけ：** 「Observer パターンを使っているシステムを日常から1つ挙げるとしたら？」

（例: メール通知、SNSのフォロー、株価アラートなど）

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 19：検索・解決力（自走力）

---

<!-- _class: no-header all-text-center align-center -->

# 名探偵の推理

<div class="highlight-box">

「犯人はお前だ！」ではなく証拠（ログ・エラー文）から追い詰める

**エンジニアの問題解決 = 証拠から原因を特定する推理**

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① 未知のエラーに出会う

<div class="experiment-box">

**【Copilot Chat → Agent モードで投げる】**

```
「JavaScriptで、意図的に以下のエラーを発生させるHTMLを作って：
・TypeError（型のエラー）
・ReferenceError（未定義の変数）
・SyntaxError（構文エラー）ではなく実行時エラーで
各エラーが発生したとき、エラーメッセージをページに表示して。
ファイル名: error-lab.html」

→ 生成されたHTMLを開いて、各エラーメッセージを確認
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② 検索ワードを Copilot に考えさせる

<div class="experiment-box">

**【表示されたエラーメッセージをコピーして、Ask モードで投げる】**

```
「以下のエラーが出ています：
[エラーメッセージを貼る]

1. このエラーの原因として考えられること
2. このエラーをGoogle検索するなら、効果的な検索ワード3パターン
3. 解決策を見つけるために確認すべきこと
を教えて。」
```

</div>

<div class="observe-box">

- エラー文を「怖いもの」ではなく「手がかり」として読む
- 検索ワードの選び方で、解決策にたどり着く速さが変わる

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 19 気づきの言語化

<br>

<div class="highlight-box">

「エラーが出た瞬間に思考停止しないためには？」

→ まずエラー文を読む → 原因を仮定する → 検索する → 試す<br><br>

**問いかけ：** 「今日のエラー解決プロセスを、名探偵の推理に例えると？」

</div>

---

<!-- _class: section -->
<!-- _paginate: false -->

## Day 20：最終課題（未来の設計図）

---

<!-- _class: no-header all-text-center align-center -->

# 建築家ごっこ

<div class="highlight-box">

設計図なしに家は建てられない

今日は「あなた自身のサービス」の設計図を描く

**4週間で学んだ言葉を全部使う**

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験① サービスアイデアを言語化する

まず自分で「作ってみたいサービス」を1つ決める（3分）

<div class="experiment-box">

**【Copilot Chat → Plan モードで投げる】**

```
「私は『[あなたのサービスアイデア]』を作りたいです。
 以下の観点で設計図を作ってください：

 1. どんなデータをDBに保存するか（CRUD で考える）
 2. フロントエンドとバックエンドの役割分担
 3. 必要なAPIは何か（外部APIか自前か）
 4. どのクラウドサービスが適しているか（IaaS/PaaS/SaaS）
 5. リリースまでの大まかなステップ

 コードは書かず、設計の説明だけ。」
```

</div>

---

<!-- _class: no-header all-text-center align-center -->

# 実験② 設計図の一部を実装する

<div class="experiment-box">

**【Agent モードに切り替えて】**

```
「先ほどの設計のうち、最もシンプルな機能を1つ選んで、
 HTML/CSS/JavaScriptで動くプロトタイプを作って。
 サーバーなし・ライブラリなし・localStorageで完結する形で。
 完成したらLive Serverで動かして確認する。」
```

</div>

<div class="observe-box">

4週間で使ったもの: Ask / Agent / Plan モード、#selection、#file、/explain、/fix、/tests

</div>

---

<!-- _class: no-header all-text-center align-center -->

# Day 20 最終振り返り

<br>

<div class="highlight-box">

1ヶ月前は呪文だった言葉を使って、自分のアイデアを語れているか<br><br>

**問いかけ：** 「今日の設計図を、1ヶ月前の自分に説明するとしたら？」

</div>

---

<!-- _class: no-header all-text-center align-center table-center table-font-large -->

# Phase 2 総まとめ — 4週間の集大成

| Week | テーマ | 学んだこと |
|------|--------|-----------|
| Week 1 | インターネットの仕組み | インターネット = レストラン / すべてのアプリは CRUD |
| Week 2 | プログラムの基礎 | 変数・型・アルゴリズム・OOP・テスト = プログラムの骨格 |
| Week 3 | クラウドとインフラ | クラウド・コンテナ・ログ・API = コードを世界に届ける仕組み |
| Week 4 | プロの思考法 | 負債・ライブラリ・設計パターン・自走力 = プロの判断軸 |

---

<!-- _class: section all-text-center align-center -->
<!-- _paginate: false -->

## おつかれさまでした！

### AI Paired Engineer 全4週間 完走！

---

<!-- _class: no-header all-text-center align-center -->

# **解散！！**
