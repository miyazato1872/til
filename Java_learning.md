```java
```
# データ型
変数に格納するデータの種類のこと
- メモリ：Rubyでいう配列のように、データを入れる箱が連続で並んでいるイメージ   
その際、数値は「2進数」に変換して扱われる
- 10進数の「100」は、2進数では「1100100」
https://www.xn--2-g90b954airby76h.net/hayamihyo-2shinsu.php


## 基本データ型の種類
<img width="745" alt="スクリーンショット 2023-02-13 17 19 01" src="https://user-images.githubusercontent.com/120078794/218406036-46eaaaab-ba1b-4a03-90fa-36a58de9438a.png">


# 変数
## 変数の宣言と使い方
```java
型名　変数名;
```
- 行末に「;（セミコロン）」
  
- 以下は必須で書くコード。
詳細は後ほど
```java
class Main {
  public static void main(String[] args) {
    //ここに処理を記述する
  }
}
```

```java
class Main {
  public static void main(String[] args) {
    int radius;
    radius = 5;
    System.out.println(radius * radius * 3.14);
  }
}
```
① int radius;によって、int型の変数radiusを宣言する  
② radius = 5;によって、変数radiusに整数の5を代入する     
③ printlnを実行して、計算結果を出力する。    

# 型推論
- 「var」を使って変数を宣言することで、値の種類によって、データ型を推論してくれて宣言と初期値の代入を同時にできる
```java
class Main {
  public static void main(String[] args) {
    var radius = 5;
    System.out.println(radius * radius * 3.14);
  }
}
```

# 代数演算子
## Javaで四則演算

```java
class Main {
    public static void main(String[] args) {
        System.out.println(1000 + 2000);
        System.out.println(3000 - 1500);
        System.out.println(50 * 40);
        System.out.println(600 / 15);
        System.out.println(5 % 2);
    }
}
```
出力結果   
3000   
1500   
2000   
40   
1   

# 比較演算子
|演算子	|使い方|	意味|
|---|---|---|
|==|	a == b|	aとbが等しい場合true|
|< |	a < b	|aがbより小さい場合true|
|> |	a > b	|aがbより大きい場合true|
|<=|	a <= b|	aがb以下の場合true|
|>=|	a >= b|aがb以上の場合true|
|!=|	a!= b	|aとbが等しくない場合true|


# Rubyの配列との違い

- 格納する要素の数を最初に決める必要があり、かつ後で要素数を変更することができない
- 要素を増やす場合は、サイズの大きな配列を新たに作成して元データをコピーするか、ArrayListというリストの一種を使用する


# 配列の使い方
- 使用する際の手順
1. 配列の宣言を行う
2. 配列の要素を作成して、入れtに代入する
3. 配列の要素に値を代入する
```java
class Main {
    public static void main(String[] args) {
      int[] scores;    //配列の宣言
      scores = new int[3];   //配列に要素を作成して、配列に代入(３つの要素を代入する受け皿を用意)
  
      scores[0] = 1;   //値の代入
      scores[1] = 5;
      scores[2] = 10;
  
      System.out.println(scores[0]);    //要素から取り出して出力
      System.out.println(scores[1]);
      System.out.println(scores[2]);
    }
}
```

## 配列の宣言方法3つ

```java
// ①配列の宣言と同時に、要素の作成も行う方法
int[] scores = new int[3];


// ②配列の宣言時に型推論を使用する方法
var scores = new int[3];


// ③配列の宣言から値の代入まで全て同時に行う方法
int[] scores = {1, 5, 10};
// この記述方法が最も簡潔だが、宣言時に代入する値が確定していない場合は使用できない

```

# リストについて
Rubyの配列と似たデータ管理の仕組みで、以下の特徴がある
- 要素を順序づけて管理する
- 要素を事後的に追加したり削除できる   
種類が2種類ある
- ArrayList
- LinkedList


## ArrayListについて
「可変長配列」を使用するための仕組み(長さ(要素数)を変更できる配列のこと
```java
import java.util.ArrayList;

class Main {
  public static void main(String[] args) {
    ArrayList<Integer> scores = new ArrayList<Integer>();   //右のように省略も可能　　ArrayList<Integer> scores = new ArrayList<>();


    scores.add(1);   //ArrayListに要素を追加するためにはaddメソッドを使用。 =>　add(要素として追加する値)
    scores.add(5);   //addメソッドを使用すると、要素はArrayListの末尾に追加される
    scores.add(10);
    scores.add(15);

    System.out.println(scores.get(0));  //要素を取り出す際は、getメソッドを使用。　=>get(取得したい要素のインデックス）
    System.out.println(scores.get(1));
    System.out.println(scores.get(2));
    System.out.println(scores.get(3));
  }
}
```
① ライブラリをインポートする    
② ArrayListの宣言を行う    
③ ArrayListに値を代入する    
④ ArrayListから要素を取り出す    

# 条件分岐(if文)
```java
class Main {
  public static void main(String[] args) {
    int value = 3;

    if (value > 0){
      System.out.println("値は正です"); 
    }
  }
}
```
```java
 if ( 条件式 ) {
      条件式を満たす時に実行する処理
 }
```
Rubyでの記述方法と異なるのは以下の点。
・条件式を（）で囲む必要があること
・行いたい処理を{}で囲む必要があること

```java
class Main {
  public static void main(String[] args) {
    int value = 3;

    if (value > 0){
      System.out.println("値は正です"); 
    }else if (value < 0){
      System.out.println("値は負です"); 
    }else {
      System.out.println("値は0です"); 
    }
  }
}
```


# 繰り返し処理(拡張for文)
Rubyのeachメソッドのようなもの


拡張for文を使用する際の構文
```java
for ( 要素を格納する変数宣言  :  配列あるいはArrayListの変数名) {
  取り出した要素を使用して行う処理
}
```
上記の記述で、以下の動作をする   
① 配列、あるいはArrayListから要素を1つ取り出す   
② 取り出した要素を変数に代入する   
③ {}内の処理を行う   
④ 配列、あるいはArrayListの要素数分だけ処理を繰り返す   

配列から要素を取り出すために、拡張for文を使う例
```java
class Main {
  public static void main(String[] args) {
    int[] scores = {1, 5, 10};

    for(int score : scores) {
      System.out.println(score);  
    }
  }
}

// 出力結果
// 1
// 5
// 10
```


ArrayListから要素を取り出す
```java
import java.util.ArrayList;

class Main {
  public static void main(String[] args) {
    ArrayList<Integer> scores = new ArrayList<Integer>();

    scores.add(1);
    scores.add(5);
    scores.add(10);
    scores.add(15);

    for(int score : scores) {
      System.out.println(score);  
    }
  }
}
```

# メソッド


## mainメソッド
mainメソッドには以下の２つのルールがある


① ファイルを実行するとmainメソッドが実行される
② mainメソッドの引数などは、必ず決められた通りに記述する必要がある

### ① ファイルを実行するとmainメソッドが実行される
```java
class Main {
  public static void main(String[] args) {  
      // ここに処理を書く
  {
}
```
上記mainメソッドの中身を定義してきたことになる


Javaのmainメソッドには、ファイルの実行時に自動的に実行されるというルールがある。そのため、mainメソッドを実行するコードを書かなくても実行される


### ② mainメソッドの引数などは、必ず決められた通りに記述する
通常のメソッドは引数の設定などを変更できるが、mainメソッドについては書き方が決められている


データ型等を変更してしまうとエラーになるため、以下の通りに記述する必要がある
```java
public static void main(String[] args) {  
      // ここに処理を書く
}
```


# 一般的なメソッドについて
① 引数を使用しないメソッドの使い方    
② 引数を使用するメソッドの使い方    
- 引数を使用しない最もシンプルな使い方   
```java
class Main {
  public static void main(String[] args) {  
    sayHello();
  }

  public static void sayHello() {
    System.out.println("Hello World");
    return;
  }
}

// 出力結果
// => Hello World
```

メソッドを定義するための構文
```java
アクセス修飾子 static修飾子 返り値のデータ型　メソッド名() {
  // 行いたい処理
}
```
<img width="638" alt="スクリーンショット 2023-02-27 23 38 05" src="https://user-images.githubusercontent.com/120078794/221592782-3e76227a-1451-4e92-b6f7-e31174c849a3.png">


Rubyでのメソッド定義と違う点は   
① 返り値のデータ型を指定する必要がある   
② 引数がないメソッドでも定義時にかっこの省略はできない   
③ Rubyの「def」「end」の代わりに、波かっこでコードを囲む 

<img width="647" alt="スクリーンショット 2023-02-27 23 42 27" src="https://user-images.githubusercontent.com/120078794/221593936-a694a47d-51d7-486a-b132-ab72b83b0918.png">


# 修飾子について
- 修飾子は、クラスやメソッド、変数などの定義を行う際に、特定の機能を付加するもの
## アクセス修飾子
<img width="637" alt="スクリーンショット 2023-02-27 23 44 32" src="https://user-images.githubusercontent.com/120078794/221594551-5ff460f4-5aa8-4406-93de-3d8ad07af20b.png">    
外部への公開範囲を設定するためのもので、以下の３種類がある。


- public   
- protected   
- private    


使用するアクセス修飾子によって、以下の設定を行うことができる

|アクセス修飾子の種類|機能|
| ------------- | ---------- |
| private       | 同一クラス内からのみアクセスできる|
| public       | どのクラスからでもアクセスできる|







