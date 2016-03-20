# Pythonハンズオン@kobe.py 第1回勉強会

これは[kobe.py 第1回勉強会](https://96698a7e745b6937f8770e9902.doorkeeper.jp/events/39381)用の資料です。

# はじめに

## 対象

* プログラミング初心者の人

## 目的

* Pythonをインストールして、Pythonプログラミングの始め方を学びます。
* Turtle Graphicsを使って、ループや条件分岐などのプログラミングの基礎を学びます。

# Pythonのインストール

まずはPythonをインストールしましょう。
最新版のPython 3.5をインストールします。
Python 2とPython 3では仕様が変わっているところもあります。
情報を集める時にはバージョンの違いに気をつけてください。

以下のいずれかの方法でインストールを行ってください。
Anacondaがおすすめです。
Windows、Mac、Linuxに対応しています。
お手元の環境に合ったインストーラーをダウンロードしてください。

## 公式インストーラー

https://www.python.org/downloads/

## Anaconda

Anacondaは、Python本体に加えていくつかの主要なライブラリ(科学技術系中心)が同梱されたパッケージです。
また、pyenvのように、Anacondaの中に複数のバージョンのPython環境を構築することができます。

https://www.continuum.io/downloads

## OS標準

MacやLinuxの多くのディストリビューションには最初からPythonがインストールされています。
他のバージョンが必要な場合は上の方法でインストールしてください。

# IPythonの実行

Windowsならコマンドプロンプト、MacかLinuxならターミナルで以下のように入力します。
`$`はコマンド行の始まりを表すのによく使われる記号で、`$`自体は入力しないでください。

```sh
$ ipython
```

## Hello World

以下のプログラムを入力して、Shiftキーを押しながらEnterキーを押してください。

```python
print('Hello World!')
```

すぐ下に`Hello World!`と表示されましたか？
`'ここに好きな文字列が書ける'`はPythonの __文字列__ です。
`print`は画面に文字列を出力する __関数__ です。
`Hello World!`を自分の好きな文字列に変えてもう一度試してみてください。

## Pythonで計算

以下のように、Pythonに計算をさせることができます。

```python
print(1 + 1) # 足し算
print(1 - 1) # 引き算
print(2 * 3) # 掛け算
print(7 / 2) # 割り算
print(7 // 2) # 割り算 (小数切り捨て)
print(7 % 2) # 割り算の余り
```

`# ここに好きな文章が書ける`は __コメント__で、人間がプログラムを理解するためのメモなどを書くことができます。
このコメントがなくてもプログラムは動きます。

もちろん小数も使えます。

```python
print(2.5 * 3 + 1.1)
```

## 変数

計算した結果を後で使うには __変数__ を使うと便利です。

```python
base = 3 * 2
print(base * 4)
```

1行目で`3 * 2`を計算した結果(=6)に`base`という名前をつけています。
2行目で`base`を使っています。

## 論理式

Pythonで数値の大小や等号などの論理条件を扱うことができます。

```python
print(1 == 1)
print(1 !== 1)
print(2 > 2)
print(2 >= 2)
print(3 < 4)
print(3 <= 4)
```

例えば、`x == y`は、`x`と`y`が等しい時は`True`になり、等しくない時は`False`になります。
`True`と`False`はPythonで真偽を表す定数です。

```python
print(True)
print(False)
```

# Turtle

ここからは、Turtleグラフィックスという学習用お絵描き用ライブラリでPythonの機能を学んでいきましょう。

## Turtleの起動

以下のプログラムを入力するとTurtleの画面が起動します。
真っ白な画面と、その中央に矢印が表示されていると思います。
この矢印を動かしながら絵を描くことができます。

```python
import tutrtle
t = turtle.Turtle()
```

1行目で`turtle`という __モジュール__ を読み込んで、使えるようにしています。
2行目で`turtle`モジュールに含まれる`Turtle`クラスの __インスタンス__ を作成し、変数`t`に格納しています。

## Turtleを動かす

Turtleの基本的な操作は以下のような感じです。
上の続きに入力してください。

```python
t.forward(100) # 100進む
t.left(90) # 左に90度回転する
t.forward(100)
t.right(90) # 右に90度回転する
t.forward(100)

```

`t.forward(x)`は、Turtleを今向いてる方向に`x`だけ前に進めます。
`t.left(x)`と`t.right(x)`は、Turtleをそれぞれ右と左に`x`度だけ回転させます。

Turtleが動いた分だけ線が描かれましたか？
最初の真っさらな状態に戻すには以下の2行を実行します。

```python
t.home() # 初期位置に戻す
t.clear() # 描いた結果を消去する
```

## 図形を描く

Turtleで簡単な図形を書いてみましょう。
まずは正三角形です。
ここまでの知識だけで正三角形を描くことができます。

```python
t.forward(100)
t.left(120)
t.forward(100)
t.left(120)
t.forward(100)
t.left(120)
```

正三角形が描けましたか？
今度は正四角形を描いてみましょう。

```python
t.forward(100)
t.left(90)
t.forward(100)
t.left(90)
t.forward(100)
t.left(90)
t.forward(100)
t.left(90)
```

`left`の回転の大きさは、正三角形の時は120(= 360 / 3)度、正四角形の時は90(= 360 / 4)度です。

## ループ

正五角形を描けそうですか？
`left`の回転の大きさを72(= 360 / 5)度にして、`forward`と`left`を5回繰り返すと良さそうですね。

なんとなくパターンが見えてきました。
それでは、正二十角形は描けそうですか？
ここまでの知識で描くことができますが、少し入力が大変そうです。
そこで、以下のように __ループ__ を使って楽をしましょう。

```python
for _ in range(6):
    t.forward(100)
    t.left(360 / 6)
```

これで`forward`と`left`を6回繰り返して正六角形を描いています。

`for`ループの使い方は以下のような感じです。
Pythonでは、どこまでが`for`ループの中身なのかは、インデントによって区別されます。
一般的には半角スペース4文字をインデントとして使います。

```python
for item in iterable:
    doSomething()
```

`iterable`の部分には __イテラブル(繰り返し可能)なオブジェクト__ というものを与えます。
`range`はイテラブルなオブジェクトの一種で、`range(x)`とすると、`0, 1, 2, ..., x - 1`の数値を順に返します。
以下のようにすると0から4までの数字が順に表示されます。

```python
for i in range(5):
    print(i)
```

正六角形を描く例では、`item`の位置に`_`を書いていますが、`item`を使わない時はこう描く場合が多いです。

## 関数

正二十角形だと以下のようになります。

```python
for _ in range(20):
    t.forward(100)
    t.left(360 / 20)
```

6の部分が20になりました。
このパターンを利用して好きな大きさの正多角形を描くことができそうです。
正n角形を描く関数を作ってみましょう。

```python
def polygon(n):
    for _ in range(n):
        t.forward(100)
        t.left(360 / n)
```

`def`は関数を定義するための文法です。
`n`を __引数__ としてとり、上で見つけたパターンに従って正n角形を描きます。
よく使う機能を関数にまとめておくことで、何度も同じことを描く必要がなくなって便利です。

関数の呼び出しは以下のようにします。
既にたくさん正多角形が描かれている場合は、一度`t.clear()`しておきましょう。

```python
polygon(3) # 正三角形を描く
polygon(7) # 正七角形を描く
polygon(10) # 正十角形を描く
```

`polygon(3)`と呼び出した時はpolygon関数の中で`n`の __値__ が3になります。

ここで、もっと小さなあるいはもっと大きな正多角形を描きたくなったとします。
例えば、1辺が50の正多角形を描く時に以下のように新たな関数を作りますか？

```python
def polygon50(n):
    for _ in range(n):
        t.forward(50)
        t.left(360 / n)
```

長さを変えるたびに新しい関数を作るのは大変そうです。
なので、1辺の長さも関数の引数として可変にしてみましょう。

```python
def polygon(n, length):
    for _ in range(n):
        t.forward(length)
        t.left(360 / n)
```

使い方は以下のような感じです。

```python
polygon(3, 10)
polygon(4, 20)
polygon(5, 30)
```

## もっとTurtleの機能を使う

これまでは黒の細い線だけを使ってきました。
色や線の太さを変えてみましょう。

```python
t.color('red') # 線を赤色にする
t.width(5) # 線の太さを5にする
polygon(3, 100)
```

また、線を描かずにTurtleを動かすこともできます。

```python
t.up() # ペンを上げる
t.forward(100) # 線は描かれない
t.down() # ペンを下ろす
t.forward(100) # 線が描かれる
```

## 条件分岐

polygon関数でnが偶数の時は赤色、奇数の時は青色の線で描いてみましょう。
__条件分岐__ を使います。

```python
def polygon(n, length):
    if n % 2 == 0:
        t.color('red')
    elif n % 2 == 1:
        t.color('blue')
    for _ in range(n):
        t.forward(length)
        t.left(360 / n)
```

2-5行目は以下のように書くこともできます。

```python
if n % 2 == 0:
    t.color('red')
else:
    t.color('blue')
```

条件分岐の文法は以下のように、はじめに`if`がきて、次に`elif`がいくつかあって、最後に`else`が来ます。
`elif`と`else`は省略することができます。

```python
if condition1:
    doSomething1()
elif condition2:
    doSomething2()
elif condition3:
    doSomething3()
else:
    doSomething4()
```

# 演習

これまで学んだことを使って、いろいろな幾何学模様を描いてみましょう。
例えば、以下のような図形が描けますか？

![kobito.1458410057.902405.png](https://qiita-image-store.s3.amazonaws.com/0/4249/d86b49d8-eb2c-043d-d378-4c74fdf3cb1c.png "kobito.1458410057.902405.png")

ここで使わなかったTurtleの機能も全て以下のドキュメントに載っています。

* [Turtle Graphics (日本語)](http://docs.python.jp/3.5/library/turtle.html)
* [Turtle graphics (英語)](https://docs.python.org/3.5/library/turtle.html)

また、以下のコマンドで公式のTurtle Demo集を見ることができます。

```sh
$ python -m turtledemo
```

# おわりに

お疲れ様でした。
このハンズオンを通じて、Pythonプログラミングの雰囲気がわかったなら幸いです。
これに満足せずにいろいろなことに挑戦してみてください。

## もっと知りたい人に

* [Pythonチュートリアル (日本語)](http://docs.python.jp/3/tutorial/index.html)
* [入門Python 3](http://www.oreilly.co.jp/books/9784873117386/)
* [実践Python 3](http://www.oreilly.co.jp/books/9784873117393/)
