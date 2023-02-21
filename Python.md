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
-　ざっくり小数点のつく数値のこと
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
