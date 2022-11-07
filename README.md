# SolenoidUNIT

ソレノイドやDCモータなどの負荷を、Grove端子から最大2個まで制御できます。負荷と電源の接続コネクタの違いで2種類あります。


## SolenoidUNIT

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/SolenoidUNIT.jpg" width="320px">

オレンジ色のコネクタ(VH3.96-4p)に、負荷用の電源と負荷を接続します。M5Stackの[BAVGソケット](https://www.switch-science.com/products/7234)を使うと、電源は2.1mmプラグ、負荷はスプリング端子で接続できて便利です。

負荷の電源はオレンジ色のVH3.96コネクタ、またはGrove端子のVDDから選択できます。Grove端子のVDDへの電源供給能力が不足する場合は[TypeC2Grove UNIT](https://www.switch-science.com/products/8453)等を使用してください。

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/SolenoidUNIT_case.jpg" width="320px">

基板形状が「[M5Stack用VH3.96-4ピンユニット[U020]](https://www.switch-science.com/products/4055)」と同一のため、そのケースを使うことができます。


### 使い方

負荷の制御は、Grove端子の2本の信号（A/B/VDD/GNDの順）で以下の通り行います。

AまたはBに"1"を与えると負荷がONとなり、"0"でOFFとなります。

必要に応じて以下のジャンパの設定を変更してください。

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/SolenoidUNIT_back.jpg" width="320px">

- JP1 : 負荷（ドライバIC）の電源の選択。VDD（VH3.96コネクタ）がデフォルト、Groveの5Vも選択可能
- JP2 : VH3.96コネクタの2番ピンの割り当て。「負荷Aのプラス側」（デフォルト）または「負荷Bのマイナス側」。
-- 「負荷Aのプラス側」（デフォルト）の場合（下図(a)）：負荷Aを1番ピン（マイナス側）と2番ピン（プラス側）に接続。負荷は1個のみ(Groveの1番ピンで制御）
-- 「負荷Bのマイナス側の場合」（下図(b)）：負荷A, Bのプラス側はVDD（3番ピン）に接続し、負荷A, Bのマイナス側をそれぞれ1番ピンと2番ピンに接続。負荷は2個（Groveの1番ピン（負荷A）と2番ピン（負荷B）で制御）

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/connection.png" width="320px">

## Solenoid5V_UNIT

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/Solenoid5V_UNIT.jpg" width="320px">

[タカハの5Vソレノイド](https://www.takaha.co.jp/co/ss/)を接続して制御できます。Grove端子のVDDへの電源供給能力が不足する場合は[TypeC2Grove UNIT](https://www.switch-science.com/products/8453)等を使用してください。

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/SolenoidUNIT5V_case.jpg" width="320px">

基板形状が「[M5Stack用VH3.96-4ピンユニット[U020]](https://www.switch-science.com/products/4055)」と同一のため、そのケースを使うことができます。

2段USBコネクタの上側がソレノイドA（Groveの1番ピンで制御）、下側がソレノイドB（Grovの2番ピンで制御）です。



## Author

Junichi Akita (akita@ifdl.jp, @akita11)




