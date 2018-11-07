# BitmexのOrderBookをWebSocketで受信しSQLiteに保存

## 概要
Bitmexの板情報(order book)は多くがWebSocketで受信可能です。
Pythonのモジュールも公開されており、それを利用してSQLiteで保存するスクリプトを作成しました。
また、直近n本のCSVへの保存と、使用例としてシステムトレードの例も書きましたが、こちらのロジックはスキャルピングの注文のやり方の例であり、実際の運用では100%損失を出します。


## 環境
Cloud9 Python3.6.5

## 使い方

```pip install -r requirements.txt```
でセットアップできます。

```trade_saving.py```

でSQLiteファイルの作成ができます。上のpythonファイルの設定によって任意の間隔で価格情報を保存できます。
```data_to_short_csv.py```

で直近360本のOHLCをCSVにしたものが常時更新されます。

scal_test.pyはAPIKeyを入力することで実際に注文まで行えますが、必ず損失を出すロジックになっていますので、ボットを動かしたい場合には書き換えてください。

## 注意
これらのスクリプトは自動取引で利益を出すロジックになっていません。仮にこのスクリプトを参考にし実際に取引を行い損失を出したとしても一切の責任を負いかねます。
