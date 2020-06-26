# サンプルコードの準備

今回自分が作成したものは`blog_sample/Webpack_sample/after`直下に`webpack-kihon`という名前でディレクトリを作成しました。ディレクトリ名はなんでもいいです。

## サンプルコード

https://github.com/miily8310s/blog_sample/tree/master/Webpack_sample

`before`フォルダがバンドル前の、`after`フォルダにバンドル後の状態を格納しています。

## サンプルコードのディレクトリ

webpack 実行前の構成は次の形にしました.

```text
─── webpack-kihon
    ├── node_modules
    ├── package.json
    ├── package-lock.json*
    ├── public
    |   ├── index.html
    |   └── js
    |       └── bundle.js
    └── src
        └── js
            ├── app.js
            └── modules
                ├── celsius.js
                └── fahrenheit.js

*yarnコマンドの場合はyarn.lock
```

## 動作確認用の html ファイル

今回のサンプルでは次のように作成しました。
`script`タブにバンドルで出力されるファイル`js/bundle.js`を指定します。

```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>webpack-sample</title>
  </head>
  <body>
    <script src="js/bundle.js"></script>
  </body>
</html>
```

## バンドルされるモジュールを作成する

webpack でバンドルされるモジュール（JavaScript ファイル）を作成します。

モジュールは`export`したメソッド関数をメインの処理を行う別の JavaScript ファイルで`import`することによって使用できる文法です。

```js
# celsius.js
export default function celsius(number) {
  return number;
}
```

```js
# fahrenheit.js
export default function fahrenheit(number) {
  return number * (9 / 5) + 32;
}
```

今回`import`するファイルは`app.js`としました。メインで行う JavaScript ファイルです。

```js
# app.js
import celsius from './modules/celsius';
import fahrenheit from './modules/fahrenheit';

const celsTemp = celsius(26);
const fahrTemp = fahrenheit(35);

document.body.innerHTML = `<p>${celsTemp} ${fahrTemp}</p>`

```
