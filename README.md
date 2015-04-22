# rensyu2
練習問題2.1～

練習問題2.1
いろいろ数字を変えて入力してみたところ、8,9 この二つが入力されるとエラーが出る。
このことからpythonでは先頭に 0 をつけた数字列を入力すると8進数が入力されたと認識すると推測される。
そして以上の事を踏まえる

>>> zipcode=02492
SyntaxError: invalid token
他の例を試すとエラーはないが、結果がおかしい：

上記は zipcode という変数に8進数を入力しようとしたのだが、
9 という数字が入っているため発進数として間違っていると言ってきていると解釈できる。

>>> zipcode=02132
>>> zipcode
1114
何が起きているか分かるかな？

では zipcode に8進数 02132 という数字が代入され、
その数字は10進数でいう 1114 であると言っているのだと解釈できる。

また、追究してみたところ
先頭が 0 で8進数、0x ならば16進数だと認識し、
別の方法では
'%o' % 10進数　で10進数を8進数に直したものを返し
'%x' % 10進数　で16進数に直したものを返す。
この時10進数のところは別の進数でも構わない。
ちなみに''で囲ったところは文字列と同じ意味を持ち変数とはならない。

str(),bin(),oct(),int(),hex()はそれぞれ、
そのまま、2進数、8進数、10進数、16進数の文字列を返す。
それぞれの頭文字は2進数から 0b, 0, 0o, 0x となる。


練習問題2.2

インタラクティブモードでの実行結果を以下に記す。
>>> 5
5
>>> x =5
>>> x+1
6

次にスクリプトモードでファイルを読み込んだところ何も反応がなかったため、print を各行に着けたところ、
c:\python>python rensyu2.py
  File "rensyu2.py", line 2
    print x = 5
              ^
SyntaxError: invalid syntax
と表示が出た。
これは print は変数の格納ではなく、計算結果を表示する機能なので、
代入文（ = ）は認識しない。
もしそれを打ち出したいときは
print "文字列"
と文字列としてうちこまなければならない。
また、SyntaxError: invalid syntax は、x が定義されていないというとエラーである。
なので、その前に 
x = 5
を入力しておき、 print x + 1 と入力すると
6
と返してくれる。
もし式も表示したいなら
print "x + 1 =", x + 1
と入力する。


練習問題2.4
１．
>>> 4*pi*5**3/3
523.3333333333334

２．ある本の定価は 24.95 ドルだが、本屋は40%の割引をしている。送料は最初の一冊で
は3 ドルで、二冊目以降は75 セントである。60 冊買うとして総額はいくらになるか？

３．わたしは 6:52am に家を出て、ゆっくりした歩行（8 分15 秒毎マイル）で1 マイル歩
き、普通の歩行(7 分12 秒毎マイル)で3 マイル歩き、再びゆっくりした歩行で1 マイ
ル歩いて帰宅したとすると何時に朝食ができるか？


練習問題2.3
以下のような実行結果になった
>>> width/2
8
>>> width/2.0
8.5
>>> height/3
4.0
>>> 1+2*5
11
>>> delimiter * 5
'.....'


