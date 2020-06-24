# インストール

webpack をインストール前に `package.json` を必ず生成してください。

## package.json の生成

npm または yarn コマンドで生成してください:

```bash
npm init -y
```

または

```bash
yarn init -y
```

生成された`package.json`を次のように修正してください。

```json
<!-- package.json -->

{
    "devDependencies": {
        "docsify-cli": "^4.4.1"
    }
}
```

## webpack のインストール

インストールする際は`webpack`だけでなく`webpack-cli`も必要です:

```bash
npm i webpack webpack-cli --save-dev
```

または

```bash
yarn add webpack webpack-cli --save-dev
```
