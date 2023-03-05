# simple-ts-node

TypeScriptを使ってNode.jsのプロジェクトを作るためのテンプレートです。  
よく使用する以下のライブラリを含んでいます。  

* [TypeScript](https://www.typescriptlang.org/)
* [Jest](https://jestjs.io/)
* [ESLint](https://eslint.org/)
* [Prettier](https://prettier.io/)

## 自分用メモ

### プロジェクトの作成

```shell
yarn init -y
```

生成された`package.json`の内容を適当に修正します。  

### TypeScriptのインストール

```shell
yarn add -D typescript ts-node ts-node-dev nodemon @types/node 
```

### TypeScriptの設定

`tsconfig.json`を作成します。  
以下のコマンドを実行します。  

```json
npx tsc --init
```

### Jestのインストール

```shell
yarn add -D jest ts-jest @types/jest
```

### Jestの設定

`jest.config.js`を作成します。  
以下の設定を追加します。  

```js
module.exports = {
  preset: "ts-jest",
  testEnvironment: "node",
  testMatch: ["**/tests/**/*.test.ts"],
};
```

### ESLintとPrettierのインストール

```shell
yarn add -D eslint prettier
yarn add -D @typescript-eslint/eslint-plugin @typescript-eslint/parser
yarn add -D eslint-config-prettier eslint-plugin-prettier
```

次に、ESLintの設定ファイルを作成します。  
以下のコマンドを実行します。  

```shell
npx eslint --init
```
