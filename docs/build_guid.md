# Build Guide

## 部品リスト

|部品名称|数|
|:-|:-|
|PCB|1|
|トッププレート(FR4)|1|
|ミドルプレート(アクリル グレースモーク 3mm)|1|
|ボトムプレート(アクリル マットクリア 3mm)|1|
|ProMicro保護プレート(アクリル グレースモーク 3mm)|1|
|スペーサー(M2 4.5mm)|4|
|スペーサー(M2 6mm)|2|
|ネジ(M2 4mm)|2|
|ネジ(M2 6mm)|10|
|ダイオード(1N4148)|14|
|スイッチ用ソケット(Kailh PCB Socket)|14|
|リセット用タクタイルスイッチ|1|
|ゴム足(小)|4|
|ゴム足(大)|2|

"Torch Edition" には以下のパーツが付属します。

|部品名称|数|備考|
|:-|:-|:-|
|バックライト&アンダーグロウ用LED(YS-SK6812MINI-E)|20|必要数:19,予備:1|

以下のパーツはキットに含まれないため、別途購入してください。

|部品名称|数|
|:-|:-|
|ProMicro|1|
|CherryMX互換キースイッチ|14|
|CherryMX対応キーキャップ(1u)|12|
|CherryMX対応キーキャップ(1u or 1.25u or 1.5u)|2|
|MicroUSBケーブル|1|

ProMicro取付用のスルーホールはコンスルー(MAC8 スプリングピンヘッダ)に対応しています。
日本国内では[遊舎工房](https://yushakobo.jp/)さんで購入することが可能です。

__部品外観図(Torch Edition)__

<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_parts.jpg" width="860">

## QMKセットアップ

キーボードファームウェアをProMicroへ書き込むため、QMK Firmwareのビルド環境が必要となります。
以下のリンクを参考に、ビルド環境をセットアップしてください。

https://docs.qmk.fm/#/ja/newbs

## パーツ半田付け

以下のパーツをPCBへ半田付けします。

1. ダイオード
2. スイッチ用ソケット
3. LED
    - LED付属モデルもしくは追加購入した場合
4. リセット用タクタイルスイッチ
5. ProMicro
    - コンスルーを利用する場合はPCBへの半田付けは不要

### PCBの確認

ProMicroのピンアサインシルクが印刷されている側が表面、ダイオードやリセットスイッチ、`MX1~MX14` までの記号シルクおよびロゴシルクが印刷されている側が裏面です。

__裏面__

<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_top_view.jpg" width="860">

### ダイオード

PCB裏面のダイオード用シルクが印刷されている箇所に、ダイオードを半田付けします。

<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_diode_position.jpg" width="480">

ダイオードには極性があります。ダイオード表面のラインが刻印されている側を、シルクの三角形頂角側に配置して下さい。

### スイッチ用ソケット

PCB裏面の `MX1~MX14` の記号シルクが印刷されている箇所に、スイッチ用ソケットを半田付けします。

<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_socket_position.jpg" width="480">

半田付けが難しい場合、PCB表面からソケットにスイッチを差し込むことでソケットを固定した状態で半田付けすることができます。

### (Option)LED

PCB裏面のスイッチホール下およびPCB内の各所に存在するLED用ノンスルーホールにLEDをはめ込み、半田付けします。
LEDには極性があるため、LED側面の4つのタブのうち、角が欠けているものがLED用ノンスルーホールのシルクと一致するよう配置して下さい。

__バックライト用LEDの場合__

バックライト用LEDの場合、LEDの底面がPCB裏面を向くよう配置します。

<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_backlight.jpg" width="480">

__アンダーグロウ用LEDの場合__

アンダーグロウ用LEDの場合、LEDの表面がPCB裏面を向くよう配置します。

<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_underglow.jpg" width="480">

LEDの取付箇所によってLEDの表裏および極性の目印用シルクの位置はそれぞれ異なります。必ずタブとシルクの組み合わせを確認してから半田付けしてください。

### リセット用タクタイルスイッチ

PCB裏面、ProMicro用スルーホール横のリセットスイッチ用シルクが印刷されている箇所に、ダイオードを半田付けします。

<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_reset_switch.jpg" width="640">

ここまでの作業が完了すると、PCB裏面は以下のような状態になっているはずです。ダイオードやLEDの実装漏れがないことを確認してください。

<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_solderd.jpg" width="860">

### ProMicro(コンスルーあり)

ProMicroにコンスルーを半田付けします。コンスルーには上下および向きがあり、樹脂部の窓がピンに近い側が半田付けをするProMicro側、反対側が半田付けをしないPCB側になります。

<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_mcu_spring_pin_header_position.jpg" width="640">

また、ProMicroへ取り付けた際に樹脂部の窓が同じ方向を向くように取り付けてください。

<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_mcu_spring_pin_header_side.jpg" width="640">

ProMicroへのコンスルーはんだ付け後、PCB表面へProMicroを取り付けてください。

### ProMicro(コンスルーなし)

コンスルーを使用しない場合、以下画像のようにピンソケットのピンが短い方をProMicroに、ピンが長い方をPCBの表面へ半田付けします。

<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_mcu_position.jpg" width="640">

ボトムプレートに干渉してしまうため、半田付け後にPCB側のピンがProMicro側と同じ程度の長さになるよう、ニッパーなどでカットしてください。

## ファームウェア書き込み

ProMicroをUSBケーブルでPCと接続し、GUI(`QMK Toolbox`)かCLI(`make`もしくは`qmk`コマンド)でファームウェアのビルドおよび書き込みを実行します。

- Reference
    - https://docs.qmk.fm/#/ja/newbs_building_firmware
    - https://docs.qmk.fm/#/ja/newbs_flashing

__makeコマンドの場合__

```zsh
$ make craftwalk:default:avrdude
```

__qmkコマンドの場合__

```zsh
$ qmk compile -kb craftwalk -km default
$ qmk flash -kb craftwalk -km default -bl avrdude
```

ファームウェアを書き込む際は、PCB裏面に半田付けしたリセットスイッチを押してProMicroをフラッシュモードにしてください。

## 組み立て

組み立て前に、以下アクリルパーツの保護紙を剥がしてください。

- ProMicro保護プレート
- ミドルプレート
- ボトムプレート
    - ロゴおよび彫刻パターン部分の保護紙は剥がしづらいため、ピンセットなどの利用をおすすめします。剥がす際に誤ってプレートに傷をつけないよう注意してください

### ProMicro保護プレート用ソケット取り付け

ProMicro取付箇所下部に、以下のようにPCB表面に配置した6mmのスペーサーをPCB裏面から4mmのネジで固定してください。

<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_mcu_spacer.jpg" width="860">

### トッププレート&ミドルプレート取り付け

トッププレートとミドルプレート、PCBを重ね合わせて以下のようにPCB表面から6mmのネジ、PCB裏面から4.5mmのスペーサーで固定してください。

<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_top_plate.jpg" width="860">
<img src="https://github.com/sotoba/craftwalk/blob/images/craftwalk_back_view.jpg" width="860">

### ボトムプレート取り付け

PCB裏面にボトムプレートを取り付け、6mmのネジで固定してください。

### ProMicro保護プレート取り付け

ProMicroの上にProMicro保護プレートを重ねて、6mmのネジで固定してください。

### キースイッチ&キーキャップ取り付け

お好みのキースイッチ、キーキャップをPCB表面から取り付けてください。PCB裏面シルクのMX13,MX14にあたるキーはお好みに応じて1u/1.25u/1.5uキーキャップを取り付けることが可能です。

### (Option)ゴム足取り付け

ボトムプレートのお好みの位置にゴム足を取り付けてください。取り付け位置によっては打鍵時に基板が傾き不安定になってしまう可能性があるため、取り付け前にゴム足を台紙から剥がさず台紙をカットして、安定して打鍵できるゴム足の配置決めをしてから取り付けてください。
