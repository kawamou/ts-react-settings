# ts-react-settings
## VSCodeとTypeScriptとESLintとPrettier
### 目標
- VSCodeでTypeScript開発。自動補完 + Lint効かせたいナア
### 前提
- VSCodeにExtensions入れただけでESLintやらが動くわけではない
- ローカルにESLintやらをプロジェクト毎にinstallする必要アリ
- VSCodeにExtensions2種類入れる
  - ESLint
  - Prettier
- VSCodeは.vscode以下のsetting.jsonを使う
  - .vscode使わない場合は下記をsettings.jsonに記入
```xxx.json
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true
},
```
### 実行
```xxx.sh
yarn install
code .

# 上記実行後、varで変数定義して保存→自動でletに変換等が確認可能

yarn start
```
### 設定は使いまわそう
- 新たなプロジェクトを作るときにもこちらの設定ファイルたちは使い回しましょう
- create-react-appと競合する部分は修正しつつ
### すべてこちらに
[りあクト！](https://github.com/oukayuka/ReactBeginnersBook-2.0/tree/master/06-lint/03-mysetting)
