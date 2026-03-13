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
---

<!-- _class: title -->
<!-- _paginate: false -->

![ponpon.USA w:150px](https://avatars.githubusercontent.com/u/238978340?v=4)
# 鉄道から学ぶアーキテクチャ #4
## 拡張と破壊 — 混雑との戦いとイノベーション

2026-02-17
ponpon.USA

---

<!-- _class: section -->
<!-- _paginate: false -->

## 前回の振り返り

---

<!-- _class: no-header all-text-center align-center -->

# 衝突を防ぐ仕組み

<br>

### 信号機（排他制御）がないと衝突する
### 同期は遅い、非同期は複雑
### 1箇所の遅延が全体に波及する

<br>

## 今日は「需要が増えた時」に注目します
## 乗客が **10倍** になったらどうする？

---

<!-- _class: section -->
<!-- _paginate: false -->

## #1 乗客が10倍になったらどうする？

---

<!-- _class: no-header all-text-center align-center -->

# 想像してください

<br>

# あなたの路線の利用者が
# **10倍** になった

<br>

## どうやって対応する？

---

<!-- _class: align-center content-image-right content-60 no-header -->

![w:500px](./assets/big-train.png)

# 選択肢1：スケールアップ

<br>

### 車両を大きくする

<br>

* 1両あたりの定員を増やす
* より強力なエンジンに換装
* = サーバーの **スペック増強**

<br>

## シンプルだが、**限界がある**

---

<!-- _class: no-header all-text-center align-center -->

# スケールアップの限界

<br>

<div class="highlight-box">
  <b>物理的限界：</b> ホームに入らない、トンネルを通れない<br>
  <b>コスト限界：</b> スペックを倍にしても、価格は倍以上<br>
  <b>単一障害点：</b> その1台が壊れたら全滅
</div>

<br>

## どこかで「天井」にぶつかる

---

<!-- _class: align-center content-image-left content-50 no-header -->

![w:500px](./assets/multiple-trains.png)

# 選択肢2：スケールアウト

<br>

### 本数を増やす / 複線化する

<br>

* 列車の数を増やす
* 線路を増設する
* = サーバーの **台数増加**

<br>

## 理論上は無限だが、**制御が難しい**

---

<!-- _class: no-header all-text-center align-center -->

# スケールアウトの難しさ

<br>

<div class="highlight-box">
  <b>調整コスト：</b> 列車同士の調整（ロードバランシング）<br>
  <b>データ整合性：</b> どの列車に乗っても同じ目的地に着く？<br>
  <b>運用コスト：</b> 監視対象が増える、障害箇所の特定が困難
</div>

<br>

## 「とりあえず増やす」だけでは破綻する

---

<!-- _class: no-header all-text-center align-center table-center table-font-large -->

# スケールアップ vs スケールアウト

<br>

| | スケールアップ | スケールアウト |
|---|---|---|
| 方法 | より大きく | より多く |
| 限界 | 物理的上限あり | 理論上は無限 |
| 複雑さ | 低い | 高い |
| コスト | 指数的に増加 | 線形に増加 |
| 障害時 | 全滅 | 一部のみ影響 |

<br>

## 正解は「どちらか」ではなく **組み合わせ**

---

<!-- _class: section -->
<!-- _paginate: false -->

## #2 破壊的イノベーション（新幹線）

---

<!-- _class: no-header all-text-center align-center -->

# ある日、経営陣が言った

<br>

# 「東京-大阪を **3時間** で結べ」

<br>

## 在来線で可能か？

---

<!-- _class: align-center content-image-right content-60 no-header -->

![w:500px](./assets/old-railway.png)

# 在来線の限界

<br>

### 既存のレールでは...

<br>

* カーブが多い → 減速が必要
* 踏切がある → 安全確保で減速
* 軌間（レール幅）が狭い → 安定しない

<br>

## **時速300km** は物理的に不可能

---

<!-- _class: align-center content-image-left content-50 no-header -->

![w:500px](./assets/shinkansen-track.png)

# 解決策：別線を敷く

<br>

### 新幹線という選択

<br>

* 専用の直線ルート
* 踏切なし（立体交差）
* 標準軌（広いレール幅）

<br>

## **リプレイス / リアーキテクチャ**

---

<!-- _class: no-header all-text-center align-center -->

# これは「作り直し」である

<br>

<div class="highlight-box">
  <b>在来線の改良：</b> 部分的な改善、既存資産を活かす<br>
  <b>新幹線の建設：</b> ゼロから設計、莫大な投資が必要
</div>

<br>

### 既存システムの「改修」では限界がある
### 本当に速くしたいなら「作り直し」が必要

<br>

## しかし、**コストと期間** は桁違い

---

<!-- _class: no-header all-text-center align-center -->

# 並行稼働の地獄

<br>

<div class="highlight-box">
  <b>新幹線の工事中も、在来線は止められない</b><br><br>
  古いシステムを動かしながら、新しいシステムを構築する<br>
  両方のメンテナンス、データ同期、切り替えタイミング...
</div>

<br>

## リプレイス案件を経験した人なら
## この辛さがわかるはず

---

<!-- _class: no-header all-text-center align-center -->

# 現実の選択

<br>

### すべてを新幹線にはできない

<br>

* 在来線は残り続ける（レガシー）
* 新幹線と在来線は **乗り換え** が必要
* 両方を運用し続けるコスト

<br>

## これが「技術的負債」との付き合い方

---

<!-- _class: section -->
<!-- _paginate: false -->

## #3 トポロジー（路線図）の設計

---

<!-- _class: align-center content-image-right content-60 no-header -->

![w:500px](./assets/hub-spoke.png)

# ハブ＆スポーク（中央集権型）

<br>

### 東京駅、新宿駅のような巨大ターミナル

<br>

* すべてが**中心**を通る
* 管理しやすい
* 中心が死ぬと**全滅**

<br>

## DBサーバー、ロードバランサー

---

<!-- _class: align-center content-image-left content-50 no-header -->

![w:460px](./assets/direct-connection.png)

# メッシュ型（分散型）

<br>

### 直通運転、相互乗り入れ

<br>

* 中心を通らずに移動可能
* 1箇所が死んでも迂回できる
* **複雑**、調整コスト大

<br>

## マイクロサービス、P2P

---

<!-- _class: no-header all-text-center align-center -->

# どこに「ハブ」を置くか？

<br>

<div class="highlight-box">
  トポロジー（路線図）の設計 = アーキテクチャ設計<br><br>
  <b>どこに集約するか</b>（DB、キャッシュ、LB）<br>
  <b>どこを分散させるか</b>（サービス、リージョン）<br>
  <b>どこで乗り換えさせるか</b>（API Gateway、BFF）
</div>

<br>

## この設計が、システムの **運命** を決める

---

<!-- _class: no-header all-text-center align-center -->

# 良いトポロジーの条件

<br>

### 1. **Single Point of Failureがない**
どこか1箇所が死んでも、全体は動き続ける

<br>

### 2. **ボトルネックが分散している**
特定のハブに負荷が集中しない

<br>

### 3. **変更の影響範囲が限定的**
1箇所の変更が全体に波及しない

---

<!-- _class: section -->
<!-- _paginate: false -->

## #4 シリーズ全体のまとめ

---

<!-- _class: no-header all-text-center align-center table-center table-font-large -->

# 4回を振り返って

<br>

| 回 | テーマ | 学び |
|---|---|---|
| #1 | 制約と標準化 | レールがあるから速く走れる |
| #2 | インターフェース | 連結器が合えば交換可能 |
| #3 | 排他制御と非同期 | 信号機がないと衝突する |
| #4 | スケーラビリティ | 限界を超えるには別線が必要 |

---

<!-- _class: no-header all-text-center align-center -->

# Key Takeaways

<br>

### 1. **スケールアップには限界がある**
いつかは「横に広げる」設計が必要になる

<br>

### 2. **本当に速くするなら「作り直し」も選択肢**
ただし、コストと期間は桁違い

<br>

### 3. **トポロジーがシステムの運命を決める**
どこにハブを置くか、の設計が最も重要

---

<!-- _class: no-header all-text-center align-center -->

# One more thing...

---

<!-- _class: no-header all-text-center align-center -->

# 技術（車両）は変わる

<br>

### 蒸気機関車 → 電気機関車 → リニア
### COBOL → Java → Go → ???

<br>

## 10年後、今の技術は「レガシー」かもしれない

---

<!-- _class: no-header all-text-center align-center -->

# でも、変わらないものがある

<br>

<div class="highlight-box">
  <b>トポロジー（路線図）</b> の設計思想<br>
  <b>ルール（レール）</b> の決め方<br>
  <b>制約と自由</b> のバランス<br>
  <b>分割と統合</b> の判断基準
</div>

<br>

## これらは **言語やフレームワークを超えて** 使える

---

<!-- _class: no-header all-text-center align-center -->

# 次のステップへ

<br>

### この4回で学んだ「設計思想」を武器に

<br>

## 「なぜこのコードはこう書かれているのか？」
## 「なぜこのアーキテクチャが選ばれたのか？」

<br>

### を **自分で判断** できるエンジニアへ

---

<!-- _class: no-header all-text-center align-center -->

# 最後の問いかけ

<br>

<div class="highlight-box">
  <b>AIが書いたコードを、そのまま信用していいか？</b><br><br>
  → 設計思想と合致しているか、<span class="red-accent-text">判断できる軸</span>を持っているか？<br>
  → レール（規約）に沿っているか、<span class="red-accent-text">見抜ける目</span>を持っているか？
</div>

<br>

## その軸があれば、AIは **最強の道具** になる
## なければ、AIに **振り回される** だけ

---

<!-- _class: no-header all-text-center align-center -->

# 最終レクチャーのお題

<br>

<div class="highlight-box">
  <b>【 課題 】</b><br>
  4回シリーズ全体を通して学んだことを<br>
  <span class="red-accent-text">「自分の言葉」</span>で5分間、発表してください<br><br>
  <b>鉄道以外のメタファーを使ってもOK</b>
</div>

<br>

## これが「出力」の総仕上げ

---

<!-- _class: no-header all-text-center align-center -->

# シリーズ完結

<br>

# お疲れ様でした！

<br>

## 次フェーズ：AI活用の実践へ

---

<!-- _class: no-header all-text-center align-center -->

# **解散！！**
