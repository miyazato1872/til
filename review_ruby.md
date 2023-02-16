### 進捗メモ：次は以下のカリキュラムから
https://master.tech-camp.in/v2/curriculums/4198
```ruby
```

# Rubyの基礎
## 式展開
- 文字列の中に式を入れることができる機能
- 文字列中で#{式}とする

```ruby
irb(main):002:0> '今日で#{20}歳になりました'
=> "今日で\#{20}歳になりました"
```

## 変数の定義
```ruby
変数名 = 格納する値
```
- 「Rubyにおいて=が1つの式は必ず『右側の値を左の変数に代入する』という意味」

## 自己代入演算子（+=, -=, *=, /=）
```ruby
number = number + 1
number += 1
# 上記は同じ意味になる
```
自己代入演算子|	例|	処理|
--- |-------------|-------------------------------|
+=	|number += 1	|numberに1足した値をnumber自身に代入
-=	|number -= 2	|numberから2引いた値をnumber自身に代入
*=	|number *= 3	|numberに3かけた値をnumber自身に代入
/=	|number /= 4	|numberを4で割った値をnumber自身に代入

## ターミナルからの入出力

### chompメソッド
```ruby
gets.chomp
# 文字列の末尾の改行を取り除く
```

## バックスラッシュ記法
- キーボードで option + ¥


|記法|	意味|
|----|----|
|\n	|改行|
|\t	|タブ|
|\b	|バックスペース|
|\\	|バックスラッシュ|


## 配列
1つの変数で複数の値を持つことのできる値。配列の中には複数の値を入れることができる。  
配列は順番で値を管理します。

```ruby
変数 = []　　#配列を生成(宣言)

pencil_case = ["ペン", "消しゴム", "定規"]
puts pencil_cas
# ↑配列の生成と呼び出し

配列 << 追加する要素 # 配列演算子(<<) 配列に新しい要素を追加したいとき
```

- 添字  
配列の各要素に割り振られた番号で、「0」から始まる。取得方法は以下
```ruby
puts pencil_case[1]

pencil_case[1] = "修正ペン" # 要素を変更する時は左記の記述
```

### lengthメソッド
例　irb  
```ruby
# 配列内の要素の数を返す
irb(main):001:0> ['あお', 'きいろ', 'あか'].length
=> 3
```

### 配列に入っている値すべてを合計するとき
```ruby
# 配列に入っている値すべてを合計したい
array = [1,2,3,4,5,6,7,8,9,10]
array.sum

# 偶数のものだけを合計したい
array = [1,2,3,4,5,6,7,8,9,10]
array.sum{ |num| num %2 == 0 }
```

参考URL（ハッシュも書いてる）
https://qiita.com/rllllho/items/94e8fde8266f14275961

## ハッシュ
関係のある複数の値を管理するときに使用   
ハッシュは、「データ」とそれに対応する「名前」のセットを要素として持つ値。  
ハッシュにおいては、データをバリュー、それに対応する名前をキーと呼ぶ。  
複数のデータを持つことのできる値という点は、配列と同じ。  
ただし、ハッシュは順番ではなく、キーで管理する。このようなキーとバリューで管理する方式をキーバリューストアという。

【例】ハッシュの宣言
```ruby
変数 = { キー1 => バリュー1, キー2 => バリュー2, キー3 => バリュー3 }
```
ハッシュのキーには、文字列も数値も使用できるが、多くの場合はシンボルという値が使用される。

## シンボル
シンボルは、見た目は文字列のようですが、コンピューターが処理するときには数値として扱われる値のことで、ハッシュのキーとしてよく用いられる。  
シンボルの宣言は、文字列の先頭にコロン:をつける。　  　　
【例】シンボルの宣言
```ruby
:文字列  
```


シンボルは見た目は文字列のようですが、コンピューターが処理するときには数値として扱われる。   
文字列を扱うよりも、数値を扱うほうがコンピューターの処理速度は速くなります。   
シンボルは数値として扱われるため処理速度が速く、文字列としての役割も果たせることから、ハッシュのキーには文字列よりもシンボルを用いることが多い


【例】シンボルをハッシュのキーに用いる際の表記の仕方
```ruby
hash = { name: "Taro" }  # よく使用されるのはこっち
hash = { :name => "Taro" }
```
###　ハッシュに値を追加する方法
【例】ハッシュへ要素を追加  
```ruby
ハッシュ[追加するキー] = 値  

# 以下は実例
student = { "name" => "John", "age" => 10 }
teacher = { name: "Mike", age: 25 }

teacher[:subject] = "English"   # これが要素の追加のコード

puts student
puts teacher
```

###　ハッシュの値を取得する方法 
```ruby
ハッシュ[取得したい値のキー]
  
# 以下は実例
student = { "name" => "John", "age" => 10 }
teacher = { name: "Mike", age: 25 }

teacher[:subject] = "English"

puts student
puts teacher
puts teacher[:name]　　　# これが取得のためのコード
```


###　ハッシュの値を変更 
```ruby
ハッシュ[変更したい値のキー] = 値
  
# 以下は実例
student = { "name" => "John", "age" => 10 }
teacher = { name: "Mike", age: 25 }

teacher[:subject] = "English"
teacher[:name] = "Emma"   #　これが変更のためのコード

puts student
puts teacher
puts teacher[:name]
```

# 配列とハッシュ 1
## 配列は、複数の値を順番で管理し1つにまとめ、ハッシュは、別々の意味を持つ複数の値同士を1つにまとめられる。このことから、配列とハッシュを組み合わせて管理をする
・出力方法はこの動画URL https://master.tech-camp.in/v2/curriculums/4194   
<img width="1613" alt="配列とハッシュの組み合わせ" src="https://user-images.githubusercontent.com/120078794/218974838-57f1e105-4eb6-4121-ba75-54beef55ce88.png">


# 配列とハッシュ 2
- 仮の値を入力した後の配列内の形
```ruby
friends =[
  {name: "将寿", height:150},
  {name: "あきとし", height:140},
  {name: "さつき", height:130}
]
```
- 取得方法と出力内容の例
```ruby
irb(main):006:0> puts friends
{:name=>"将寿", :height=>150}
{:name=>"あきとし", :height=>140}
{:name=>"さつき", :height=>130}

irb(main):007:0> puts friends[1]
{:name=>"あきとし", :height=>140}

irb(main):008:0> puts friends[1][:height]
140
```

### 条件分岐
- if文  
【elsifによる複数の条件分岐】
```ruby
if 条件式1
  # 条件式1が真(true)のときに実行する処理
elsif 条件式2
  # 条件式1が偽(false)のとき、かつ
  # 条件式2が真(true)のときに実行する処理
else
  # 条件式1と条件式2がどちらとも偽(false)のときに実行する処理
end
```

## 繰り返し処理　(ループ処理)

### timsメソッド
```ruby
数値.times do |ブロック変数|
  # 繰り返す処理
  # 繰り返しの回数を使う場合、ブロック変数を使用する
end
```  
### ブロック、ブロック変数
- ブロックとは、doとendで囲まれた処理のまとまりのことです。doの後に|任意の変数名|と記述することでブロック変数を定義できる。   
- ブロック変数とは、ブロック内でのみ使用できる変数のこと。  
timesメソッドにおいては、繰り返し処理が1回実行されるごとに、ブロック変数に0から1ずつ増加する数値が代入される

## 配列に同じ処理を繰り返す  
配列のすべての要素に対して繰り返し処理を行いたい場合には、eachメソッドを使う

### eachメソッド
配列やハッシュの要素1つ1つに対して、要素の数だけ繰り返し処理が行えるメソッド  

```ruby
[配列 or ハッシュ].each do | [変数] |  # doの横にブロック変数（ | [変数] |）を記載している
  # 処理
end
```
繰り返し処理が実行されるたびに、配列またはハッシュの値がそれぞれブロック変数に格納され、その値を処理の中で使用できる

## ブロック変数の動きのイメージ
- ハッシュ  
```ruby
# 期待する出力
りんご : 150
オレンジ : 200
バナナ : 100
パイナップル : 300

# ハッシュの値として｛果物の名前：果物の値段}を作成し、そのハッシュに対してeach文を実行することで以下のように実現できる

fruits = { りんご: 150, オレンジ: 200, バナナ: 100, パイナップル: 300 }
fruits.each do |key, value|
  puts "#{key} : #{value}"
end
```
  
- 配列
```ruby
# 期待する出力
りんご
オレンジ
バナナ
パイナップル

# 値をそれぞれ配列に格納させ、その配列に対してeach文を実行することで以下のように実現できる。

fruits = ['りんご', 'オレンジ', 'バナナ', 'パイナップル']
fruits.each do |item|
  puts item
end
```

- 配列の中にハッシュが入っている場合
```ruby
# 期待する出力
りんごの重さは100gです
オレンジの重さは80gです
バナナの重さは150gです
パイナップルの重さは300gです

# 値をそれぞれ配列に格納させ、その配列に対してeach文を実行することで以下のように実現できる。

fruits = [
  {name: "りんご", weight: 100},
  {name: "オレンジ", weight: 80},
  {name: "バナナ", weight: 150},
  {name: "パイナップル", weight: 300}
]

fruits.each do |fruit|
  puts "#{fruit[:name]}の重さは#{fruit[:weight]}gです"
end
```

### timesメソッドよる繰り返しの補足　(ブロックの使い方)
```ruby
#　期待する出力
1回目の繰り返し
2回目の繰り返し
3回目の繰り返し
4回目の繰り返し
5回目の繰り返し
6回目の繰り返し
7回目の繰り返し
8回目の繰り返し
9回目の繰り返し
10回目の繰り返し

# 書き方①
10.times do |i|
  puts "#{i + 1}回目の繰り返し"
end

# 書き方② (ブロックが1行の場合には次のように記述することもできる)
10.times {|i| puts "#{i + 1}回目の繰り返し" }

```

## 1〜10までの数字を順番に足し合わせていくプログラム
```ruby
sum = 0
10.times do |i|
  sum += i + 1
end

puts sum

# 期待する出力は　55 
```
<img width="438" alt="スクリーンショット 2023-02-16 16 16 00" src="https://user-images.githubusercontent.com/120078794/219295496-71ebcaf0-67b2-4fb9-aeb1-fb0499bdb25c.png">


# メソッドの概要
- 戻り値  
<img width="678" alt="スクリーンショット 2023-02-16 16 34 49" src="https://user-images.githubusercontent.com/120078794/219298269-7328a654-24b2-4886-b700-cac6e2804719.png">

## メソッドに変数を渡す

### 変数が使える範囲(スコープ)   
<img width="703" alt="スクリーンショット 2023-02-16 16 37 12" src="https://user-images.githubusercontent.com/120078794/219298952-06e641ef-3bad-45a8-aff6-e11ad9703a84.png">   

<img width="697" alt="スクリーンショット 2023-02-16 16 36 53" src="https://user-images.githubusercontent.com/120078794/219298875-55e30b68-f7f8-488e-8d80-86ad55122df4.png">  

<img width="649" alt="スクリーンショット 2023-02-16 16 40 24" src="https://user-images.githubusercontent.com/120078794/219299363-5b8dc011-6aaf-412e-b4c0-520bba990591.png">   

<img width="651" alt="スクリーンショット 2023-02-16 16 40 31" src="https://user-images.githubusercontent.com/120078794/219299415-c25e3c33-9ce1-4bf0-a7be-268918d0b620.png">   

<img width="628" alt="メソッドのスコープ" src="https://user-images.githubusercontent.com/120078794/219299661-777db4bf-6893-41b3-81a7-f70419b47a41.png">   

# メソッドに引数を使って変数を渡す方法
- スコープ
-　仮引数
-　実引数
- 戻り値  

<img width="476" alt="1" src="https://user-images.githubusercontent.com/120078794/219301219-25390bf2-7f94-44a6-be86-39692cddef0d.png">

<img width="522" alt="2" src="https://user-images.githubusercontent.com/120078794/219301256-e640989d-2a09-4d3e-9511-1fa420119e39.png">

<img width="502" alt="3" src="https://user-images.githubusercontent.com/120078794/219301299-31362bc0-5fa7-4201-9afd-a78096bed81f.png">

<img width="633" alt="4" src="https://user-images.githubusercontent.com/120078794/219300822-60a79e91-397b-48a8-a712-3d3a422c6391.png">

<img width="598" alt="5" src="https://user-images.githubusercontent.com/120078794/219300857-01822478-c9b9-48a5-9dfd-656fbb086dbe.png">

<img width="581" alt="6" src="https://user-images.githubusercontent.com/120078794/219300870-be56934e-71d9-4874-a3f8-78eb705db3d4.png">

<img width="531" alt="7" src="https://user-images.githubusercontent.com/120078794/219300882-403df54c-3c03-48df-a7b1-11704942304e.png">

<img width="732" alt="スクリーンショット 2023-02-16 16 53 13" src="https://user-images.githubusercontent.com/120078794/219302101-4e61b2c1-5da5-4ddb-829c-a2918cc1cbad.png">


## return文
メソッド内でreturn ◯◯と記述すると、returnの後ろに続けた式がそのメソッドの戻り値になる。  
returnを利用した時点で戻り値が決まり、メソッドはその行の処理を終えると強制的に終了する。  

【例】　　
```ruby
def sample
  "1"
  "2"
  "3"

  return "4"  # ここで処理は終わり

  "5"         # 呼ばれない
  "6"         # 呼ばれない
end

puts sample   # => 4
```

### 引数
引数は、メソッドなどに渡すことのできる値のこと。  
引数によって、メソッドは外にある変数（スコープ外の変数）の値をメソッドの中で扱うことができる。
- 実引数と仮引数の実用例

```ruby
# 期待する出力は両方とも「9」となります

# 例①
def sample(number)  # ②仮引数numberで、実引数「3」の値を受け取る
  puts number * number  # ③「3」が代入されたnumberを使って「3 * 3」を行い出力する
end

sample(3)  # ①数値「3」を実引数にしてメソッドを呼び出し


# 例②
def sample(value)  # 仮引数は「value」
  puts value * value
end

number = 3
sample(number)  # 実引数は「number」

```

###　引数は複数用意ができる
左から順に「第一引数」「第二引数」...「第○引数」と呼ぶ   
【例】引数の呼び方
```ruby
def メソッド名(第一引数, 第二引数)
  # 処理
end

メソッド名(第一引数, 第二引数)
```
実引数と仮引数の数は、必ず一致している必要があり、引数の数が一致していない場合は、エラーが生じる。

### 複数の引数をメソッドで使う
<img width="1530" alt="複数の引数を使ったメソッド" src="https://user-images.githubusercontent.com/120078794/219307105-0c1b29e4-9c20-4841-aa61-958b9f36a727.png">

# times,eachメソッドのスコープ
times,eachメソッドのスコープ範囲は、def〜endで定義するメソッドと違いがある   
<img width="685" alt="スクリーンショット 2023-02-16 17 20 39" src="https://user-images.githubusercontent.com/120078794/219307818-868d2d2e-0def-4783-8de7-bb87ec35c03a.png">

<img width="712" alt="スクリーンショット 2023-02-16 17 24 40" src="https://user-images.githubusercontent.com/120078794/219309626-d61701ad-78c0-440d-bfbd-42713eb5f138.png">

# メソッドの定義、times、eachを用いたミニアプリ　ローラーコースターのコード

```ruby
def judge_height(list)
  ride_count = 0
  list.each do |friend|
    if friend[:height] >= 130
      puts "#{friend[:name]}さんは乗車できます"
      ride_count += 1
    else
      puts "#{friend[:name]}さんは乗車できません。。。。"
    end
  end
  puts "乗車するのは#{ride_count}人です"
end

def add_friends(list)
  friend = {}
  puts "お友達の名前は？"
  friend[:name] = gets.chomp
  puts "お友達の身長は？"
  friend[:height] = gets.to_i
  list << friend
end

friends = []

3.times do
  friends = add_friends(friends)
end

judge_height(friends)

```

上記の入力するパターンと期待する出力は以下   
【ターミナル】
```ruby
# 出力  お友達の名前は？
## 入力  たろう
# 出力  お友達の身長は？
## 入力  160
# 出力  お友達の名前は？
## 入力  じろう
# 出力  お友達の身長は？
## 入力  120
# 出力  お友達の名前は？
## 入力  さぶろう
# 出力  お友達の身長は？
## 入力  150

# 出力  �たろうさんは乗車できます
# 出力  じろうさんは乗車できません。。。。
# 出力  さぶろうさんは乗車できます
# 出力  乗車するのは2人です
```

###まとまった処理には名前をつけてメソッドとして定義しておくべきこと。
なぜなら、プログラムは処理の結果が大切であり、処理の過程が見えている必要はないため。　　
もし過程となる処理の中身を意識するときにも、それらはまとまっていた方が読みやすくなる。　　
   
また、メソッドを定義すればその中の変数や処理は、スコープによって他の処理に影響を与えないことがわかっているため、安心してコードを書きやすくなる。
