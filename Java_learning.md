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


# 配列の使い方
- 使用する際の手順
1. 配列の宣言を行う
2. 配列の要素を作成して、入れtに代入する
3. 配列の要素に値を代入する




