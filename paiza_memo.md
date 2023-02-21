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

### 二次元配列　
```ruby
n = gets.to_i
roster = Array.new(n)  #長さがnの配列を生成

n.times do |i|   # n回繰り返す
  roster[i] = gets.split(' ')   # 配列roster[0]から順番に、右のような型で二次元配列で保存される[[ユーザーA,32],[ユーザーB,27],[ユーザーC,40]]
end

roster.each do |member|  # 二次元配列のroster[0]から順番に繰り返し、配列内の要素をそれぞれ変数に代入する roster[0]に該当する[ユーザーA,32]からeach開始
  name = member[0]  #[ユーザーA,32]の"ユーザーA"を変数nameに代入
  age = member[1].to_i  # [ユーザーA,32]の"32"を数値として変数ageに代入

  puts "#{name} #{age + 1}"    #「ユーザーA 33」として出力して、eachの最初に戻ってroster[1]で同じ処理を繰り返す
end
```

### while文
- 指定した条件式が真(true)の間、繰り返し実行する
```ruby
# 基本構文
while 条件式　do
実行する処理１
実行する処理２
end


# コード例
num = 0
while num <= 2 do
 num += 1
end

# 実行結果
# 0
# 1
# 2
```
### sprintf フォーマット
- 出力を右詰めにして余った左側に希望する数の0を詰める方法
```ruby
p sprintf("%010d", 10)   #=> "0000000010"
```
参考URL  https://docs.ruby-lang.org/ja/latest/doc/print_format.html


### splitメソッド
- 文字列を分割して配列にするためのメソッド   
引数に任意の文字を指定することで、その指定した文字で配列内で分割することができる。
```ruby
# 参考例①
str = "samurai,engineer,blog" 
array = str.split(",") 
p array

# 出力結果
# ["samurai", "engineer", "blog"]


# 参考例②
str = "123456" 
array = str.split("34")
p array

# 出力結果
# ["12", "56"]
```
- 他にも応用として正規表現を使用して細かな条件での分割や1文字ずつ分割する方法もある   
参考URL　➡︎  https://www.sejuku.net/blog/41681
