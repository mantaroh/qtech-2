### q-tech Meeting #2

 ## レガシーソフトウェア(序章)

 [mantaroh(@_mantaroh_)](https://twitter.com/_mantaroh_)

>>>

 ## about:me

>>>

### 仕事

 所属: Systec Co.Ltd.,

 肩書：Software engineer

>>>

### 家庭

 肩書：共同CEO 兼 CFO

---

 # はじめに少し告知

>>>

 ## 「かごもく」にて、
 ## 「レガシーソフトウェア」を
 ## 扱った勉強会を開催します。
 ## 詳細は「かごもく」！

---

 # レガシーソフト
 # ウェアとは？

>>>

 # これを見てね
 ![レガシーソフトウェア改善ガイド](https://www.seshop.com/original/images/product/18976/LL.jpg)

>>>

 # 〜完〜

>>>

 ## アンハッピーな開発
 * 利害関係者が多く、仕様がなかなか決まらない
 * 現在のドキュメント=ソースコード
 * 開発前に動作調査が必要
 * バグ混入に気づきにくい
 * 毎日のように市場障害と戦う
 * 秘伝の技が多い

>>>

```
＿人人人人人人人人人人人人人人人人人人＿
＞　本来のシステム開発に集中できない　＜
＞　          疲弊が漂う        　＜
￣Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y￣
```

>>>

 ## ハッピーな開発
 * 新しい技術にチャンレジ出来る
 * 標準的な技術を使っている
 * 開発環境構築・ビルド・リリースが早い
 * 本来の設計やコーディングに集中できる

>>>

 ## ソフトウェアエンジニア
 # = 知的生産者

---

  # レガシーあるある

  ### 注:過去の会社をディスってるわけじゃないです

>>>

 ### 1.古いツールチェイン

>>>

```
 とあるプロジェクトの開発環境リスト

 Windows アプリ：
  - Visual Studio 2003
  - .Net Framework 1.1

 Web アプリ：
  - Java SDK 1.5
  - Apache Struts
  - Oracle Database 9g

 Mobile アプリ
  - Android API Level 14 (ICS)
  - Eclipse

```

>>>

<p style='color: red'>Qiita say 'この記事は3年以上経過しています'</p>

>>>

 ### 2.ドキュメントが。。

>>>

```
とあるプロジェクトのドキュメント

* 基本設計書
  Lotus Notes DB

* 詳細設計書・結合テスト仕様書
  Microsoft Excel

* バグトラッキング
  Lotus Notes DB

* ソースコード
  Microsoft VSS

```

>>>

 個人的な感想：
 * ソフトウエアエンジニアが多くのツールを同時に扱うとパフォーマンスが下がる
 * 開発設計書がソースに近くないと剥離していく
 * そもそもドキュメントのレベルがまちまち

>>>

 ### 3.影響範囲が予測不能

>>>

```
例：
// 外部モジュールから参照されてる
var USER_KUBUN = 0;    // この区分に [3 : Student] 追加したい
…
function updateUser(KBN) {
   this.USER_KUBUN=KBN;
}
…
function getKUBUNString() {
  if (USER_KUBUN == 0) 
    return “Administrator”;
  else if (USER_KUBUN == 1) 
    return “Premium”;
  else if (USER_KUBUN ==2)
    return “Free”;
  else
    return “Unknown”;
}
```

>>>

 `USER_KUBUN` が色んなところから参照されており、変更による影響が予測不能。。

>>>

  ### 4. ソフトウェア手工業

>>>

```
例： とあるプロジェクトのリリース手順

１）リリース担当者は最新ソースコードをリリース専用マシンにコピー
２）リリース専用マシンでコードをビルドし、成果物を仮リリース
　　フォルダにコピーして、メールを送信
３）テスターはメールに記載されているオブジェクトをテスト
４）テスト不合格したら修正＆リリースを繰り返す
```

>>>
