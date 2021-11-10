# LaTeX にスタイルファイルを追加したい

なんか色々動かなかったからやったこと一覧

ちなみに環境はwindowsのwsl上で動かしてて、
```
win10 home 21H1
wsl2 Ubuntu 20.04.3 LTS
```
って感じ

## だいたいどれもこんなもん

`.sty`か`.ins`をDLしてきて`mktexlsr`すればよい

`.ins`は解凍（？）方法として`latex [filename].ins`しなきゃだけど

## LaTeX Error: File `q.sty' not found.

-> `apt install texlive`

だけ

[参考文献(stackoverflow)](https://stackoverflow.com/questions/28214878/file-q-sty-not-found-latex-linux)

## LaTeX Error: File 'jlisting.sty' not found.

1. [ここ](https://osdn.net/projects/mytexpert/downloads/26068/jlisting.sty.bz2/)から`jlisting.sty.bz2`をDL
1. `/usr/share/texlive/texmf-dist/tex/platex`に移動<br>
そんなディレクトリねぇよ！って人は`texmf-dist/`を見つけてその下へ
1. `sudo mkdir jlisting`してディレクトリを作る
1. DLしてきた`jlisting.sty.bz2`をさっきのディレクトリに移動
1. `bunzip2 jlisting.sty.bz2`で解凍する<br>
`bunzip2`とか通らないが？って人は`sudo apt install bzip2`する
1. `sudo mktexlsr`してLaTeXに登録

##  LaTeX Error: File 'jvlisting.sty' not found.

1. [ここ](https://ctan.org/tex-archive/macros/latex/contrib/jvlisting)から`jvlisting.zip`をDL
1. `/usr/share/texlive/texmf-dist/tex/platex/`に移動させる
1. `sudo unzip jvlisting.zip`
1. `cd jvlistng & sudo latex jvlisting.ins`
1. `sudo mktexlsr`

<!-- https://www.ctan.org/tex-archive/macros/latex/contrib/here -->
