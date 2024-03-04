# SolenoidUNIT

ソレノイドやDCモータなどの負荷を、Grove端子から最大2個まで制御できます。負荷と電源の接続コネクタの違いで2種類あります。


## SolenoidUNIT

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/Solenoid_UNIT.jpg" width="240px">

オレンジ色のコネクタ(VH3.96-4p)に、負荷用の電源と負荷を接続します。M5Stackの[BAVGソケット](https://www.switch-science.com/products/7234)を使うと、電源は2.1mmプラグ、負荷はスプリング端子で接続できて便利です。

負荷の電源はオレンジ色のVH3.96コネクタ、またはGrove端子のVDDから選択できます。Grove端子のVDDへの電源供給能力が不足する場合は[TypeC2Grove UNIT](https://www.switch-science.com/products/8453)等を使用してください。

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/Solenoid_UNIT_case.jpg" width="240px">

基板形状が「[M5Stack用VH3.96-4ピンユニット[U020]](https://www.switch-science.com/products/4055)」と同一のため、そのケースを使うことができます。


### 使い方

ソレノイドとの接続は、電源供給方法に応じて以下の2通りがあります。制御方法は後述します。

#### ACアダプタ等から供給する場合

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/Solenoid_usage1.jpg" width="160px">

ソレノイドの定格電圧が12V等の5Vよりも高い電圧の場合は、ACアダプタ等をオレンジ色コネクタのVS-G間、ソレノイドをA+とA-Bの間に接続します。（M5Stackの[BAVGソケット](https://www.switch-science.com/products/7234)を使うと、電源は2.1mmプラグ、負荷はスプリング端子で接続できて便利です）

#### Grove端子から供給する場合

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/Solenoid_UNIT_back.jpg" width="160px">

一般のソレノイドは5Vでは駆動できませんが、5Vで駆動する場合は、電源をGrove端子から供給することができます。
裏面のJP1の、中央-VS(上側)の端子がつながっていますので、カッター等でカットし、中央と反対側の"Grove5V"側を、ハンダを盛るなどしてショートします。これによって、負荷への電源がGrove側の+5Vから供給されます。
ただし、一般にソレノイドは消費電流が多く、マイコン側の+5V電源の供給能力が不足する場合がほとんどです。そのような場合は、[TypeC2Grove UNIT](https://www.switch-science.com/products/8453)を使用して、負荷側の電源をUSB Type-C端子から供給することができます。別途USB-CコネクタのACアダプタ等を接続してください。

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/Solenoid_usage2.jpg" width="160px">

#### 2個のソレノイドを制御する場合

必要に応じて、2個のソレノイドを制御することができます。ただし接続がやや複雑ですので、ご注意ください。

- JP2 : VH3.96コネクタの2番ピンの割り当て。「負荷Aのプラス側」（デフォルト）または「負荷Bのマイナス側」。
  - 「負荷Aのプラス側」（デフォルト）の場合（下図(a)）：負荷Aを1番ピン（マイナス側）と2番ピン（プラス側）に接続。負荷は1個のみ(Groveの1番ピンで制御）
  - 「負荷Bのマイナス側の場合」（下図(b)）：負荷A, Bのプラス側はVDD（3番ピン）に接続し、負荷A, Bのマイナス側をそれぞれ1番ピンと2番ピンに接続。負荷は2個（Groveの1番ピン（負荷A）と2番ピン（負荷B）で制御）

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/connection.png" width="320px">


## Solenoid5V_UNIT

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/Solenoid5V_UNIT.jpg" width="320px">

[タカハの5Vソレノイド](https://www.takaha.co.jp/co/ss/)を接続して制御できます。

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/Solenoid5V_UNIT_case.jpg" width="320px">

基板形状が「[M5Stack用VH3.96-4ピンユニット[U020]](https://www.switch-science.com/products/4055)」と同一のため、そのケースを使うことができます。

2段USBコネクタの上側がソレノイドA（Groveの1番ピンで制御）、下側がソレノイドB（Grovの2番ピンで制御）です。

マイコン（M5Stack等）との接続は以下のように行います。

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/Solenoid5V_usage1.jpg" width="320px">

ただしソレノイドは通電時の消費電流が大きいため、マイコン側の電源供給能力が不足する場合があります。その場合は、[TypeC2Grove UNIT](https://www.switch-science.com/products/8453)を使用して以下のように接続してください。負荷側の電源はUSB Type-C端子から供給することができます。別途USB-CコネクタのACアダプタ等を接続してください。


<img src="https://github.com/akita11/SolenoidUNIT/blob/main/Solenoid5V_usage2.jpg" width="320px">


## マイコン(M5Stack等)からの制御

ソレノイドのの制御は、Grove端子の2本の信号（A/B/VDD/GNDの順）で行います。AまたはBに"1"を与えると負荷がONとなり、"0"でOFFとなります。SolenoidUnitの標準接続（ソレノイド1個）ではA端子のみを使います。

UIFlowでの[使用例](Solenoid5V_test.m5f)（以下）を参考にしてください。（Core2のPortAに接続した場合。A=GPIO32、B=GPIO33）

<img src="https://github.com/akita11/SolenoidUNIT/blob/main/Solenoid5V_test.png" width="320px">


## Author

Junichi Akita (akita@ifdl.jp, @akita11)




