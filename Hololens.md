# HoloLens 2

## 公式ドキュメント

- <https://learn.microsoft.com/ja-jp/hololens/hololens-core-components>
- <https://www.microsoft.com/ja-jp/hololens/industry-manufacturing>

## 開発ドキュメント

- <https://learn.microsoft.com/ja-jp/windows/mixed-reality/develop/development>

## AR, VR, MR の違い

| 用語                  | サービス例                                      | 必要デバイス例                   |
| --------------------- | ----------------------------------------------- | -------------------------------- |
| AR(Augmented Reality) | ポケモンGo, Amazon「ARビュー」                  | スマートフォン                   |
| VR(Virtual Reality)   | PlayStation VR                                  | VRゴーグル(Meta Quest)           |
| MR(Mixed Reality)     | Dynamics 365 Remote Assist, Dynamics 365 Guides | MRゴーグル(Hololens, Vision Pro) |

これらを総称して XR(eXtended Reality) と呼ぶ

## Dynamics 365 Remote Assist

- <https://dynamics.microsoft.com/ja-jp/mixed-reality/remote-assist/>
- <https://learn.microsoft.com/ja-jp/dynamics365/mixed-reality/remote-assist/overview-hololens>

- 音声コマンドを使用する際は「Remote Assist」に続けて「元に戻す」などのアクションを声で指示する

## Dynamics 365 Guides

- <https://dynamics.microsoft.com/ja-jp/mixed-reality/guides/capabilities/>
- <https://learn.microsoft.com/ja-jp/dynamics365/mixed-reality/guides/overview>
- <https://learn.microsoft.com/ja-jp/dynamics365/mixed-reality/guides/create-guide>
- <https://learn.microsoft.com/ja-jp/dynamics365/mixed-reality/guides/pc-app-anchor>

## Mixed Reality 開発ツール

- [MRTK(Mixed Reality Toolkit)](https://learn.microsoft.com/ja-jp/windows/mixed-reality)
- Unity
- Unreal Engine

## 音声認識

- 「選択」と言うと視線カーソルが表示される
- 視線カーソルをターゲットに合わせて「選択」と言うと、そのオブジェクトが選択される
- スタートメニューに視線を合わせて「設定」と言うと、設定アプリを起動する
- ウィンドウのxボタンの上に視線カーソルを移動し、「閉じる」と言うと、ウィンドウが閉じる
- 利用可能な音声コマンドを確認するには、ホログラムに視線を合わせて「話してください」と言う
- 「スタートに移動」と言うと、スタートメニューを開く
- イマーシブアプリを終了するには、「スタートに移動」と言ってスタートメニューを表示し、ホームボタンを選ぶか、音声コマンド「Mixed Reality ホーム」と言う
- 「次のステップ」と言うことで、ガイドの次のステップに進む
  
## 基本操作

- 手の届かないホログラムを選択するには、手のひらから出る光線をホログラムに合わせて、人差し指と親指をくっつける(エアタップ)
- ホログラムを大きくするには、ボックスの隅にあるハンドルのいずれかを掴んだままにしてドラッグする
- ホログラムを回転させるには、ボックスの側面のハンドルを掴んでドラッグする
- 片手でスタートメニューを開くには、手のひらを自分の方に向けたままにして、手首の上に表示されるホログラムに視線を合わせて、ホログラムを見続けながら親指と人差し指を使ってピンチする
- イマーシブアプリを終了するには、スタートメニューを表示し、ホームボタンを選択する

## 録画

<https://learn.microsoft.com/ja-jp/hololens/holographic-photos-and-videos>

- [音量を上げる] ボタンと [音量を下げる] ボタンを同時に押したままにすると録画できる

## Windows Device Portal

IPアドレスを確認する方法

- 「自分のIPアドレス」と発音する
or
- [設定] > [ネットワークとインターネット] > [Wi-Fi] > [接続先] > [プロパティ] > [IPアドレス]

- https://<HoloLens の IP アドレス>
- <https://192.168.1.8>
- <https://192.168.128.103>

### 画面共有

- [Windows Device Portal] > [Views] > [Mixed Reality Capture] > [Live Preview] > [Start]

## QR コード アンカーを使用してガイドを固定

<https://learn.microsoft.com/ja-jp/dynamics365/mixed-reality/guides/operator-anchor#anchor-your-guide-by-using-a-qr-code-anchor>

### QR コード アンカーのベスト プラクティス

<https://learn.microsoft.com/ja-jp/dynamics365/mixed-reality/guides/pc-app-anchor-qr-best-practices>

- [ ] 幅 101 mm ～ 400 mm で印刷することを推奨
  - それよりサイズの小さいQRコードを使用する際の注意点
    - 極端にコードに近い位置に目を置くことが必要になる場合がある
    - 照明条件の変化にも影響を受けやすくなる
    - 反射点がある場合、情報の読み取りに影響が生じ、アンカーの読み取りができなくなることがある
- [ ] 理想的なスキャン距離は 50 〜 150 cm
- [x] 30%のグレー背景が推奨

### QR コード アンカーについて自宅で検証

- QRコードのサイズ : 4cm x 4cm
- QRコードの背景 : グレー
- QRコードとカメラの距離 : 44cm
- 読み取りが正常に行えている状態から、条件を1つだけ変更して検証を行った

| 変更条件                                     | 結果 |
| -------------------------------------------- | ---- |
| 距離を極端に近づけた(27cm)                   | 〇   |
| 距離を離した(60cm)                           | ✕    |
| 斜めから読み取り                             | ✕    |
| シーリングライトの設定を暖色に変更           | 〇   |
| シーリングライトを消した                     | ✕    |
| シーリングライトを消した状態でライトを点けた | ○    |
| 鏡面の上で読み取り                           | ○    |
