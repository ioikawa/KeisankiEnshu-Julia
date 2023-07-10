# PyPlotによるグラフ描画

## `PyPlot.jl` パッケージによるグラフ描画
Pythonには matplotlib という有名な描画ライブラリがあり，
PyPlotというインターフェースを介してグラフを描画することができる．

ここでは，Juliaから PyPlotを呼び出すパッケージ（インターフェース） [`PyPlot.jl`](https://github.com/JuliaPy/PyPlot.jl) を使ってグラフを描画する方法を説明する．

!!! note
    `PyPlot.jl` は PyPlotのインターフェースなので，基本的には （Pythonの）PyPlotと同じ方法で動作する．
    [公式のチュートリアル](https://matplotlib.org/stable/tutorials/introductory/pyplot.html#)
    に書いてあるPythonコードをJulia向けに少し書き直せばそのまま動く（はず）．

!!! note
    Julia言語の標準的な描画パッケージは現時点では存在しないが，
    有名なものとしては [`Plots.jl`](https://docs.juliaplots.org/latest/) というパッケージがある．．
    `Plots.jl` は様々な描画ライブラリに対するフロントエンドであり，
    [`GR`](https://gr-framework.org/) や `PyPlot` などといった描画ライブラリを呼び出すことができる（このようなライブラリをバックエンドという）．
    `GR` は `PyPlot`に比べて簡単に使えるので便利だが，まだ v1.0未満（現時点で v0.66.0）のためか，細かいところで完成度の低い印象がある．

## 準備
Pythonライブラリを呼び出すためのPyCallと，matplotlibをあらかじめインストールしておく必要がある．

### matplotlibのインストール
Python側でmatplotlibのインストールを行う．例えば，`pip`コマンドで次を実行する．
```
$ pip install matplotlib
```

### PyCallのインストール
Julia側でPyCallのインストールを行う．
インストールの手順は[こちら](https://github.com/JuliaPy/PyCall.jl)を参照．
基本的には `pkg> add PyCall` で問題なくインストールされるが．
環境によってはエラーが発生するようなので要注意．

## PyPlot.jlパッケージの追加
PyCallとmatplotlibが適切にインストールされていれば特に問題なく終わるはず．
```
$ julia
julia> ]  
pkg> add PyPlot
 [...]
```

動作確認として，$[0,1]\times [0,1]$内にランダムに10個の点を取り，順番に線を結んだグラフを描いてみる．
```@repl
using PyPlot
clf()        # 描画のクリア
plot(rand(10), rand(10), marker="o");
savefig("plot-test.png"); 
close()     # プロット閉じる．実行時には外してください．
```

![plot](plot-test.png)


## グラフ描画: plot

```@example
using PyPlot
#clf()              # 描画のクリア
figure()      # 直前に描いたグラフと重なるのを防ぐため
grid()
x = -2pi:0.1pi:2pi    
plot(x, sin.(x))  
savefig("plot-sin.png")
close()     # プロット閉じる．実行時には外してください．
```
![plot](plot-sin.png)


