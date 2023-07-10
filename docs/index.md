```@example
using Dates; today()
```

# はじめに

## Julia言語とは
- Julia言語は **数値計算向けに設計された汎用プログラミング言語** である．
- 数値計算プログラムが書きやすく，実行速度も速い．
- 比較的新しい言語である：2018年にバージョン 1.0 がリリースされ[^1]，言語仕様が正式なものとなった．
- MATLABやPythonはプログラムを書きやすいが，インタプリタ型言語ゆえに実行速度が遅いというデメリットがある．
- Julia言語ではJITコンパイルなどの現代的な技術を駆使して，プログラムの書きやすさと実行速度を高度なレベルで両立させている．

## 特徴
- 文法・構文に関してはMATLABから大きな影響を受けている．
- MATLABと同様に数学関数，有理数，複素数，任意精度計算，線形代数，などの数学に関する多数の機能が標準で実装されている．
- MATLABはプロプライエタリ（ソースコード非公開）であるが，Julia言語はオープンソース 
- MATLABやPythonはインタプリタ型（＋動的型付け）なのでコードを簡潔に書きやすいが，その代償として実行速度が遅くなる．
  Julia言語はJITコンパイル等により実行速度の損失を小さく抑えている．実際に，最速のC言語と比べてもおよそ数分の1と評価されている．[^2]

[^1]: https://julialang.org/blog/2018/08/one-point-zero/ 
[^2]: https://julialang.org/benchmarks/

!!! note 
    Julia言語は数値計算に最適なプログラミング言語であるが，
    数値計算用に特化されているわけではないし，
    他の言語ではできないことを可能にするような魔法の言語ではない．  
    これは裏を返せば，Julia言語に関する知識の大部分は普遍的で他言語で通用するということでもある．

!!! note 
    Juila言語ではプログラムの初回実行時にJITコンパイルが行われる．初回は（JITコンパイル）＋（プログラムの実行時間）がトータルの実行時間になるので，遅く感じるかもしれない．
    2回目以降はJITコンパイルは行われないので，プログラム本来の実行時間になる．

## 参考文献
- [公式サイト: The Julia Language](https://julialang.org/)
- [公式ドキュメント(en)](https://docs.julialang.org/en/v1/) ：ここに全て書いてあるので検索してください．
- 進藤・佐藤: 「[1から始めるJuliaプログラミング](https://www.coronasha.co.jp/np/isbn/9784339029055/)」コロナ社，2020.  本学では電子版が閲覧可：[Maruzen eBook](https://elib.maruzen.co.jp/elib/html/BookDetail/Id/3000091727?5)
- Kalicharan: *Julia - Bit by Bit*, UTICS, Springer, 2021. 
  [SpringerLink(Tulips経由)](https://link-springer-com.ezproxy.tulips.tsukuba.ac.jp/book/10.1007/978-3-030-73936-2)


