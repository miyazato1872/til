```java
```
# データ型
変数に格納するデータの種類のこと
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
```java
class Main {
  public static void main(String[] args) {
    var radius = 5;
    System.out.println(radius * radius * 3.14);
  }
}
```
