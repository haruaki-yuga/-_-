# パッチノート

## v1.0.3(2024/11/29マージ予定)

* ページ更新時の入力情報の保持に対応しました。
* セーブ・ロード機能を追加しました。
* フォームデータのエクスポート・インポート機能を追加しました。
  * エクスポートボタンを押すと、クリップボードにフォームの入力内容をjson化した文字列がコピーされます。以下に例示してあります。
  * インポートボタンを押すとテキスト入力を求める画面が開かれます。エクスポートで得た文字列をペーストすると、 __フォームへ__ 変更が反映されます。セーブが必要なら別途行ってください。

```json
{
  "name": "プレイヤー1",
  "hp": 100,
  "ap": 10,
  "attack": 20,
  "subAttack": 5,
  "speed": 10,
  "critical": 5,
  "fumble": 15,
  "drama": 10,
  "hit": 10,
  "evasion": 5,
  "defense": 10,
  "resistance": 10,
  "mobility": 4,
  "attackRangeChecks": {
    "0": true,
    "1": false,
    "2": false,
    "3": true,
    "4": false
  },
  "activeSkills": {
    "0": "",
    "1": "",
    "2": "",
    "3": "",
    "4": ""
  }
}
```

## v1.0.2 hotfix(2024/11/29 18:48修正済)

* 次の不具合を修正しました。
  * レンジ補正の適用ロジックの不具合

## v1.0.2(2024/11/29マージ済)

* 通常攻撃の射程距離とレンジ補正、移動処理を実装しました。
* 次の不具合を修正しました。
  * 命中度による抵抗・ドラマ減少がダメージ処理後も継続する不具合
  * 回避クリティカル・ファンブルの判定に命中判定のダイスロール結果が用いられていた不具合
    * あさがきらきらさんご報告ありがとうございます！
  * グレイズヒット・ライトヒット時に副攻を参照していた不具合
    * あさがきらきらさんご報告ありがとうございます！
* 次の仕様を反映しました。
  * 速度持ち越し時、持ち越せる速度は自身の速度を上限とする

## v1.0.1(2024/11/27マージ済)

* 各判定のクリティカル・ファンブル処理に対応しました。
* 20ターン終了時点で決着がつかない場合の勝敗判定を追加しました(ppp闘技場基準)。
* 次の不具合を修正しました。
  * ドラマ判定でのクリティカルと速度の強化回数に10回の上限が付与されていない不具合
  * 攻撃を受ける側の行動値が40ぴったりの際に条件漏れにより無限ループに陥る不具合
