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
