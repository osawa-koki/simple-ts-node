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

```shell
npx tsc --init
```

### Jestのインストール

```shell
yarn add -D jest ts-jest @types/jest
```

### Jestの設定

`jest.config.js`を作成します。  
以下のコマンドを実行します。  

```shell
npx jest --init
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

これだとうまくいかないケースがあるので、そのような場合は以下の内容に書き換えます。  

```.eslintrc.js
module.exports = {
  env: {
    browser: true,
    es2021: true
  },
  extends: [
    'eslint:recommended',
    'plugin:@typescript-eslint/recommended',
    'plugin:prettier/recommended',
  ],
  parser: '@typescript-eslint/parser',
  parserOptions: {
    ecmaVersion: 12,
    sourceType: 'module'
  },
  plugins: ['@typescript-eslint', 'prettier'],
  rules: {
    // additional rules
  }
};
```

---

次に、Prettierの設定ファイルを作成します。  
`.prettierrc`というファイルを作成し、以下の内容を記述します。  

```.prettierrc
{
  "trailingComma": "es5",
  "tabWidth": 2,
  "semi": true,
  "singleQuote": true
}
```

### ビルドスクリプトの作成

`package.json`にビルドスクリプトを追加します。  

```json
{
  "scripts": {
    "dev": "ts-node-dev ./src/index.ts",
    "start": "nodemon --exec ts-node ./src/index.ts",
    "lint": "eslint --ext .ts ./src --fix --max-warnings 0",
    "prettify": "prettier --write ./src/**/*.ts",
    "test": "jest"
  }
}
```
