# Leinigen

Leiningenとはclojureの依存性管理や各種タスクを実行するツール  
他の言語でいうところの   
`maven, gradle, sbt, pyenv+virtualenv+pip, rbenv+bundler`  
に相当する  

Leinigenと同じポジションのツールとして[boot](https://github.com/boot-clj/boot)があるが  
今の所leiningenがデファクト

leiningen はタスクを実行するまでの起動, ロード時間が


新規プロジェクトを生成
- lein new <project name> [template name]   
  実行すると `$PWD/<project name>` というディレクトリが作成され、
  そのディレクトリの中に project.clj, src/, test/, .gitignore などが作成される

プロジェクトの依存関係を
- lein repl

依存関係取得,ビルド,デプロイなど
- lein deps
- lein install
- lein deploy
- lein jar
- lein uberjar



## インストール
OS X  
`brew install leiningen`  

Linux
`(write here later)`

Windows
`(write here later)`

## 設定ファイル
マシン内グローバルな設定  
```
$HOME/.lein/
        | indices/
        | self-installs/
        | profiles.clj  <-- 触るとすればここくらい
        | repl-history
```


プロジェクトローカルな設定  
`$PROJECT_ROOT/project.clj`

## プロジェクトの作成
