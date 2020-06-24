# 設定ファイルの作成

設定ファイルの`webpack.config.js`を作成します。

## 今回設定した内容

```js
const path = require("path");

module.exports = {
  mode: "development",
  entry: "./src/js/app.js",
  output: {
    filename: "bundle.js",
    path: path.resove(__dirname, "public/js"),
  },
};
```

## 設定項目について

### mode

`mode`は`development`・`production`・`none`のいずれかを設定します。

`development`は開発用、`production`は本番用となります。

なお入力必須です。

### entry

`entry`はエントリーポイントを設定します。
エントリーポイントはモジュールを読み込んでメインの処理をする JavaScript ファイルのこと。

### output

`output`は出力するファイル名・出力先を指定します。
