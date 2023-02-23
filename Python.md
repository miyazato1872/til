- Python 言語リファレンス
https://docs.python.org/ja/3/reference/index.html

- Python3 系 基礎文法 - Qiita
http://qiita.com/rohinomiya/items/aab6b16d1a470871713c

# print関数
```Python
# デフォルトで末尾に改行がある
print("Hello")
print("World")

# => Hello
# => World



# 末尾をカンマにするコード
print("Hello", end=",")
print("World")

# => Hello,World



#  末尾を空文字列にするコード
print("Hello", end="")
print("World")

# => HelloWorld
```
# データ型
- 整数を扱う int 型や、文字列を扱う str 型など
### 浮動小数点数
- ざっくり小数点のつく数値のこと。/を使うとこれになる。//は整数になる
- 浮動小数点数の型は、int関数を使って小数点以下を切り捨てて整数にできる
```python
print(813)
print(8.13)

print(1)
print(1.0)

print(int(3.14))
print(int(3.8))
```
出力結果
```python
813
8.13
1
1.0
3
3
```

# Pythonの演算子
- 算術演算子
- 代入演算子
- 算術演算子
- ブール演算子
- 比較演算子   

```python
print(6 + 2)
print(2 - 6)
print(3.14 + 2.71)
print(8 + 3.13)
print

# => 8
# => -4
# => 5.85
# => 11.129999999999999

# コンピュータが小数を正確に表現できないことにより誤差が発生することがある(+、-、*、/、//、全てにおいて同様)
```
## 割り算の/と//の違い
- // 演算子は、演算結果が小数のとき、その数を小さい方の整数を解として得ることができる
```python
print(6 // 2)
print(6 / 2)

print(3.14 // 2.71)
print(3.14 / 2.71)

print(8 // 3.13)
print(8 / 3.13)

print(-13 / 4)
print(-13 // 4)
```
出力結果
```python
#　=> 3
#　=> 3.0
#　=> 1.0
#　=> 1.1586715867158672
#　=> 2.0
#　=> 2.5559105431309903
#　=> -3.25
#　=> -4
```

## 余りを求める
```python
print(5 % 2)
 
# =>1
# Rubyと同じ
```

## べき乗を求める
- べき乗演算とは 2 の 3 乗のような演算のこと (この 2 の 3 乗は 2 を 3 回掛ける演算なので、2 × 2 × 2 = 8 が演算結果になります)
このように同じ数を何度も掛けていく演算をべき乗演算という   
演算子は、**を使用する
```python
print(5 ** 2)
print(5 ** 3)

#=> 25
#=> 125

## 数値演算の優先順位
普段の計算と同じで、足し算引き算より掛け算割り算。   
余り%も掛け算とかと同じ優先順位になる
掛け算や割り算より、べき乗が最優先される
```ruby
print(12 * 8 ** 3)

# => 6144
```


# 変数への代入
- 基礎的なコードはRubyと同じ
```python
num = 5
num_2 = num
print(num_2)

num_3 = num + 1
print(num_3)

# => 5
# => 6
```

# 累算代入演算子
- Rubyの代入演算子と同じ考え
```python
num = 1
num += 2  # num = num + 2 と同じ意味
print(num)

num = 1
num -= 1  # num = num - 1 と同じ意味
print(num)

num = 2
num *= 12  # num = num * 12 と同じ意味
print(num)

num = 2
num /= 2  # num = num / 2 と同じ意味
print(num)

num = 2
num //= 2  # num = num // 2 と同じ意味
print(num)

num = 7
num %= 5  # num = num % 5 と同じ意味
print(num)

num = 5
num **= 2  # num = num ** 2 と同じ意味
print(num)
```
### Python は再代入する際に型を変更することができる
```python
a = "paiza"
print(a)

a = 813
print(a)

# => paiza
# => 813
```
型を横断する再代入を繰り返すコードは、コードのデバッグ時にトラブルの原因になりうるので望ましいとはいえない

# 文字列のインデックスiの取得
- Rubyの配列の添字のようなもの
```python
s = "Hello, World!"
print(s[0])
print(s[-1])  # 文字列 s の末尾の文字列が出力される
print(s[-2])  # 文字列 s の末尾から 2 番目の文字列が出力される

# => H
# => !
# => d
```
## 文字列のインデックス i ~ j-1 の部分文字列を取得する方法
- 文字列の取得したい範囲を指定するということ
- s[i:j] のように書くと、文字列 s のインデックスが i から j-1 までの部分文字列を取得することができる

```python
s = "Hello, World!"
print(s[1:4])

# => ell
#この時、[1:4]は、インデックスの4の文字の前までという意味になるので、「ell」までということになる

s = "Hello, World!"
print(s[:5])
print(s[7:])
print(s[:])

# => Hello
# => World!
# => Hello, World!


# => s[:j] のように指定すると、先頭の文字列からインデックスが j-1 の文字列までの部分文字列を取得できる。逆も同様
```

