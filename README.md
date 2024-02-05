# React Native + Expo

[Expo](https://expo.dev/)

- Expo SDK
	- Expo でアプリを作るために必要なあれこれを集めたパッケージ
	- 3ヶ月に１回の定期リリース
	- React NativeでもExpo Modules（旧unimodule）として利用可能
- Expo CLI
	- Expo で開発するときに便利なツールを集めた CLI
		- init: アプリの雛型を生成する
		* install: Expo SDK と互換性のある npm パッケージをインストールする
		* start: 開発サーバーを起動する
		* build: iOS/Android/Web 向けにアプリをビルドする
		* publish: expo.dev のサーバーにアプリをアップロードする。OTA アップデートもできる
- Expo Go
	- Expo でアプリを開発するためのクライアント。いわゆるシミュレーターと異なり、手元のスマートフォン上で動く
	- Expo Go には Expo SDK に含まれていないネイティブコードを呼び出すことはできないという制約がある。
- Expo Snack
	- ブラウザで試せるPlaygroundツール
	- 課金で順番待ちをスキップできる
- Expo Application Services (EAS)
	- 次世代のExpo Cli
	- CI/CDが可能
		- build: アプリのバイナリをビルドすることができる。
		- submit: Expo が運営するサーバーから App Store と Google Play Store にアプリをアップロードすることができる。
		- update: OTAアップデート


## 開発環境の構築
[Installation - Expo Documentation](https://docs.expo.dev/get-started/installation/)

3つのネットワーク
- localhost
- LAN
- Tunnel(expo.devを通して)

Expo Goの使い方

---

## 標準コンポーネント
[Core Components and Native Components · React Native](https://reactnative.dev/docs/intro-react-native-components)

特徴
1. コンポーネントの利用にはインポートが必要
2. OSによっては利用できないものもある

[View Flattening · React Native](https://reactnative.dev/architecture/view-flattening#:~:text=View%20Flattening%20is%20an%20optimization,great%20model%20for%20intuitive%20development.)

## 標準API
ネイティブのAPIをJSをを通して呼び出す

[AccessibilityInfo · React Native](https://reactnative.dev/docs/accessibilityinfo)

### ネイティブモジュールの利用
[Camera - Expo Documentation](https://docs.expo.dev/versions/v44.0.0/sdk/camera/)

## スタイリングについて
[Style · React Native](https://reactnative.dev/docs/style)

インラインでは`<View style={{backgroundColor: "#fff"}}>`

CSSとの違い
- 「-」の代わりにキャメルケース
- 基本単位がdp(デバイス密度非依存ピクセル)
	- 異なるたん丸の異なる解像度でも同じように表示
- FlexBoxが基本

[Layout with Flexbox · React Native](https://reactnative.dev/docs/flexbox)

### UIライブラリ
- [NativeBase: Universal Components for React & React Native](https://nativebase.io/)
- [RNUILib](https://wix.github.io/react-native-ui-lib/)
- [React Native Paper](https://reactnativepaper.com/)
- [React Native Elements | React Native Elements](https://reactnativeelements.com/)
- [UI Kitten - React Native UI Library based on Eva Design System](https://akveo.github.io/react-native-ui-kitten/)

## ルーティングについて
-  [React Navigation](https://reactnavigation.org/) 
-  [react-native-navigation](https://github.com/wix/react-native-navigation) 
 
[Navigating Between Screens · React Native](https://reactnative.dev/docs/navigation)

---

## Eslint and Prettier
```
yarn add -D eslint-config-universe

yarn add -D eslint prettier @typescript-eslint/eslint-plugin @typescript-eslint/parser
```

※ @react-native-community/eslint-config

- package.json
```json
{
  "eslintConfig": {
    "extends": "universe/native"
  },
}
```

- .prettierrc
```
{
  "tabWidth": 2
}
```

## React Navigation
```
yarn add @react-navigation/native

expo install react-native-screens react-native-safe-area-context
```
https://reactnavigation.org/docs/getting-started/


```
yarn add @react-navigation/native-stack @react-navigation/stack
```

* stack：左右にスライドしながら画面を切り替える < native stack
* tabs：タブを選択することで画面を切り替える
* drawer：画面端から現れるサイドメニューで画面を切り替える


## Nativebase
```
yarn add native-base

expo install react-native-svg

expo install react-native-safe-area-context
```