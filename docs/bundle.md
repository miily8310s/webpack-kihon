# バンドルする

いよいよ JavaScript ファイルのバンドルを行います。

## npm scripts について

今回のバンドル作業では`npm scripts`というものが使用します。

作成した`package.json`には`"scripts"`を記入しています。

```json
<!-- package.json -->

### 一部省略
  "scripts": {
    "build": "webpack"
  }
}

```

これにより`npm run build`とコマンドで入力することで実際にバンドルを行ってくれる`webpack`コマンドを代わりに入力してくれます。

`webpack`コマンドを直接入力しても問題ないですが、明文化的な意味で`package.json`に記載してしまったほうがいいです。
