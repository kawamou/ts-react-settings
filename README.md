# ts-react-settings
## 目標
- VSCodeでReact(TypeScript)開発
- Lint + フォーマッター効かせたい
## 前提
- VSCodeにExtensions入れただけでESLintやらが動くわけではない
- ローカルにESLintやらをプロジェクト毎にinstallする必要アリ
- VSCodeにExtensions2種類入れる
  - ESLint
  - Prettier
- VSCodeは.vscode以下のsetting.jsonを拾う
  - .vscode使わない場合は下記をsettings.jsonに記入
```xxx.json
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true
},
```
## 実行
```xxx.sh
git clone [THIS_REPOSITORY]

yarn install
code .

# 上記実行後、varで変数定義して保存→自動でletに変換等が確認可能

yarn start
```
## 自分で一から作る場合(ミニマム構成)
- Extentions(ESLintとPrettier)入れる
- settings.jsonに追記
```xxx.json
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true
},
```
- 諸々設定
```xxx.sh
yarn init
yarn add -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin
yarn add -D prettier eslint-config-prettier eslint-plugin-prettier
yarn add -D typescript
npx tsc --init
vim .eslintrc.json
```
- .eslintrc.jsonの内容
```xxx.json
{
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:@typescript-eslint/recommended-requiring-type-checking",
    "plugin:prettier/recommended",
    "prettier/@typescript-eslint"
  ],
  "plugins": ["@typescript-eslint"],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "sourceType": "module",
    "project": "./tsconfig.json"
  },
  "env": { "browser": true, "node": true, "es6": true },
  "rules": {
  }
}
```
- VSCode開くとLintとフォーマッター効いてるはず
## 参考
- [VSCodeでESLint+typescript-eslint+Prettierを導入する](https://qiita.com/madono/items/a134e904e891c5cb1d20)
- [りあクト！](https://github.com/oukayuka/ReactBeginnersBook-2.0/tree/master/06-lint/03-mysetting)
