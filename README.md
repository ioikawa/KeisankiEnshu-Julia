# 全学計算機システム
Ubuntu 20.04にJulia 1.6.7 がインストール済み．
ここではサテライト室のPC端末を想定して，JuliaとJuypter Notebookの導入方法を説明する．

※ Windowsには導入されていません．

## Ubuntu の起動

端末の電源を入れて起動させると，OSの選択画面が表示されるので，
`Ubuntu 20.04` を選択する．

詳細は[ICTガイド](https://www.cc.tsukuba.ac.jp/ICT/ICT_Guide_J.pdf)を参照．

## Terminalの起動
`[Ctrl] + [Alt] + [T]` （同時押し）でTerminalを起動する．

- `pwd`：カレントパスの表示
- `date`：日付の表示
- `cal`：カレンダーの表示
- `ls`  カレントフォルダのファイル一覧
- `cd <移動したいフォルダ名>` 指定したフォルダに移動する．
  - `cd ..` ひとつ上のフォルダに移動する．
  - `cd` （引数なし）ユーザーフォルダに移動 
- `mkdir <フォルダ名>` フォルダを指定した名前で作成
- `[Ctrl] + [d]` or `[Ctrl] + [c]`: プログラムの終了
- `[TAB]`：パスやコマンドの補完
- `[↑]` or `[Ctrl]+[p]` : 一つ前に実行したコマンドを表示する．繰り返し可能．
参考：[The Linux command line for beginners](https://ubuntu.com/tutorials/command-line-for-beginners#1-overview) 
 
## Julia言語の起動

2023年11月2日時点では，Julia 1.6.7 のフルパスを入力して起動する．
（単に `$ julia`　と実行すると v1.9.3　のJuliaが起動する．
v1.9.3 では Jupyter Notebook上で正常に動作しないので注意．）

```
$ /usr/local/bin/julia
```

`Version 1.6.7`と表示されていることを確認する．

```
   _       _ _(_)_     |  Documentation: https://docs.julialang.org
  (_)     | (_) (_)    |
   _ _   _| |_  __ _   |  Type "?" for help, "]?" for Pkg help.
  | | | | | | |/ _` |  |
  | | |_| | | | (_| |  |  Version 1.6.7 (2022-07-19)
 _/ |\__'_|_|_|\__'_|  |  Official https://julialang.org/ release
|__/                   |

julia> 
```


## IJuliaパッケージの追加とJupyter Notebookの起動
Jupyter Notebook上でJuliaが動作するように設定する．
```
julia> ]　　# ] キーを押して pkgモードに入る 
pkg> add IJulia    
pkg> build IJulia   
julia> using IJulia
julia> notebook()
```
正常にインストールされていれば，ブラウザが起動し，Jupyter Notebookが表示される．
新規ノートブックを作成し，kernelとして `Julia 1.6.7`を選択する．
試しに，一番上のセルに
```
versioninfo()  # Shift+Enter
```
を入力して実行する．起動時と同様に出力されればOK．
