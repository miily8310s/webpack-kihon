# サンプルコードの準備

今回は`webpack-kihon`という名前でディレクトリを作成します。ただしディレクトリ名が別になっていても問題ありません。

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
