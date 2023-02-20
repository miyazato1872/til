```ruby

```
- 以下の2つのコードは同じ標準入力と標準出力になる (変数を定義して配列にデータを保存するかどうかの違い)
```ruby
10.times { puts gets }
```
```ruby
num = []
10.times do
  num << gets
end

puts num
```

- 以下の2つのコードは同じ標準入力と標準出力になる (変数を定義して配列にデータを保存するかどうかの違い)
```ruby
n = gets.to_i
puts n * 100
```
```ruby
puts gets.to_i * 100
```

### 配列の多重代入
```ruby
s, t = 'Hello paiza'.split(' ')
puts s
puts t

# 期待する出力
# Hello
# paiza
# 'Hello paiza'の部分をgetsにすることで、標準入力で与えることができる


# 数値として取得する方法
a, b = gets.chomp.split(" ").map(&:to_i)
```
```ruby
a, b = [1, 2, 3] # a = 1; b = 2
a, b, c = [1, 2, 3] # a = 1; b = 2; c = 3
a, b, c, d = [1, 2, 3] # a = 1; b = 2; c = 3; d = nil

```

### ブロックパラメーター
```ruby
"one two three four five".split(' ').each do |val|
  puts val
end
```
```ruby
'one two three four five'.split(' ').each { |val| puts val }
```
上記2つとも期待する出力は以下になる  
one  
two  
three  
four  
five  
になる


### maxメソッド
```ruby
numbers = [1, 2, 3, 10, 4, 5]
max = numbers.max
puts max

# 出力：
# 10
```

### maxメソッド
```ruby
numbers = [1, 2, 3, 10, 4, 5]
max = numbers.max
puts max

# 出力：
# 10
```
### joinメソッド　

```ruby
array = ["apple", "grape", "orange"]

puts array.join(' ')
# => apple grape orange



array = ["1", "2", "3"]

puts array.join(' ')
# => 1 2 3

```

### Arrayクラス
- new  join. timesを使って標準入力、横並びに半角区切りで標準出力をする
```ruby
n = gets.to_i
arr = Array.new(n)   # Array.newで配列を生成。その配列の長さは、newの引数(n)で入力された数値で決めてる
  n.times do |i|　　　# ブロック変数の|i|は、0から始めてn.timesの回数を繰り返す 0,1,2,3,4...
    arr[i] = "paiza"   # 変数arr(配列)の引数の場所[i]→0,1,2,3,4...の場所に、"paiza"を入れていく
  end
puts arr.join(' ')   #　arrに入った要素"paiza"n個を、putsで出力する。その際に、joinメソッドを使って(' '）を使って繋いで出力している
```

- 改行区切りでの出力   
整数nを与えられて、次の行で半角スペース区切りでn個の整数を与えられる。それを改行区切りで出力する
```ruby
n = gets.to_i   #2行目で入力する数値の数
arr = gets.split(" ").map(&:to_i)   #arrに配列として数値を保存している作業[5, 6, 10, 3, .... ]

arr.each do |num|  # 配列arrの要素数と同じ数だけeachによって繰り返されて、num[0]、num[1]、num[2]...の順番でarrの値がnumに代入される
  puts num   #  arrの要素が代入されたnumがputsで出力される　num[0]、num[1]、num[2]...
end

```


