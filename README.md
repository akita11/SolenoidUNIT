# SolenoidUNIT

ソレノイドやDCモータなどの負荷を、Grove端子から最大2個まで制御できます。

負荷と電源の接続コネクタの違いで2種類あります。
いずれも基板形状が「[M5Stack用VH3.96-4ピンユニット[U020]](https://www.switch-science.com/products/4055?_pos=1&_sid=744f12cc4&_ss=r)」と同一のため、そのケースを使うことができます。


## SolenoidUNIT

負荷の電源はオレンジ色のVH3.96コネクタ、またはGrove端子のVDDから選択できます。

Grove端子のVDDへの電源供給能力が不足する場合は[TypeC2Grove UNIT](https://shop.m5stack.com/collections/m5-sensor/products/usb-typec2grove-unit)等を使用してください。

### 使い方

JP1 : 負荷（ドライバIC）の電源の選択。VDD（VH3.96コネクタ）がデフォルト、Groveの5Vも選択可能
JP2 : VH3.96コネクタの2番ピンの割り当て。負荷Aのプラス側（デフォルト）または負荷Bのマイナス側。
- 負荷Aのプラス側（デフォルト）の場合：負荷Aを1番ピン（マイナス側）と2番ピン（プラス側）に接続。負荷は1個のみ(Groveの1番ピンで制御）
- 負荷Bのマイナス側の場合：負荷A, Bのプラス側はVDD（3番ピン）に接続し、負荷A, Bのマイナス側をそれぞれ1番ピンと2番ピンに接続。負荷は2個（Groveの1番ピン（負荷A）と2番ピン（負荷B）で制御）

## Solenoid5V_UNIT

[タカハの5Vソレノイド](https://www.takaha.co.jp/co/ss/)

Grove端子のVDDへの電源供給能力が不足する場合は[TypeC2Grove UNIT](https://shop.m5stack.com/collections/m5-sensor/products/usb-typec2grove-unit)等を使用してください。

2段USBコネクタの上側がソレノイドA（Groveの1番ピンで制御）、下側がソレノイドB（Grovの2番ピンで制御）


## Author

Junichi Akita (akita@ifdl.jp, @akita11)




