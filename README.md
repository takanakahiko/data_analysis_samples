# 用語説明

***

## 特徴量とは

- データが持つ属性のようなもの

例:「国語の点数」「数学の点数」が特徴量

||国語の点数|数学の点数|
|:-:|:-:|:-:|
|山田くん|70|90|
|田中くん|60|80|
|...|...|...|
|中山くん|40|30|

***

## クラスタリングとは

データが

- 内的結合(同じラベルは近い)
- 外的分離(違うラベルは遠い)

を満たすようにラベル付けすること

例)山田君と田中君は点数が近いので同じクラスに振り分けるのが望ましい

***

# 機械学習・深層学習

*** 

## AI周辺技術

![image.png](https://qiita-image-store.s3.amazonaws.com/0/96206/ba580d41-5260-5361-0ea3-82dac20dc6cf.png)

- 深層学習は機械学習の一部
- AI=ディープラーニングじゃない

***

## 機械学習の進め方

- "何"から"何"を予測するか決める
- データを収集する
- データを成形する
- 学習する
- テストする
- 検証する

***

## "何"から"何"を予測するか決める

- どのデータの
- どの特徴量を用いて
- 何を判定するか
- 例)顔から名前を予測

***

## データを収集する

- 特徴量と正解データのセットを入手
- 例)LFW Face Database

![image.png](https://qiita-image-store.s3.amazonaws.com/0/96206/c49930a5-4dd1-bead-5a86-fcd0c4d70e5e.png)


***

## データを成型する

ターゲット

||画素1|画素2||画素m|
|:-:|:-:|:-:|:-:|:-:|
|画像1|254.|254.|...|86.|
|...|...|...|...|...|
|画像n|39.|50.|...|133.|

ラベル

||画像１|画像2||画像n|
|:-:|:-:|:-:|:-:|:-:|
|ラベル|5|6|...|5|

***

## 学習させる

いろいろモデルがある

- SVM : データを区分する線分を学習
- CNN : 脳細胞を模したモデルを学習
- 決定木学習 : 決定木を学習

ポイント

- 学習用データとテスト用データは分ける
- **特徴量の配列からラベルを求める点は基本的に変わらない**

***

## 検証

モデルが実際に判定できるかテストする

|  | 画像1 | 画像2 | ... | 画像n |
|:-:|:-:|:-:|:-:|:-:|
| 正解ラベル | 5  | 3  | ... |  4 |
| 判定結果 |  2 |  3 | ... |  4 |
| 合否 | x | o | ... |  o |

スコアの出し方は色々ある

- 正解率 : 全データ中、いくつ正解だったか
- 再現率 : 取りこぼしが多くないか
- 精度　 : 間違えたピックアップが多くないか

***

# プログラミング言語

***

## python

- 強力なパッケージ(ライブラリ)が豊富
- パッケージマネージャによる管理
- 記述量が少ない(体感)
- **ソースコードが読みやすい**

```python:hello.py
print("Hello World!!")
```

**今回はpython3を対象とします**

***

### 基本的な構文１

Hello World

```java:Test.java
Class Test(){
  public static void main(){
    //コメントは'//'
    System.out.println("Hello World");
  }
}
```

```python:test.py
# コメントは'#'
print("Hello World") # セミコロン不要
```

***

### 基本的な構文2

変数宣言

```java:Test.java
int a = 1;
double b = 1.2;
String c = "テスト";
```

```python:test.py
a = 1 #型の指定は不要
b = 1.2 #代入される値で型が決定
c = "テスト" #文字列も同様
```

***

### 基本的な構文3

if文

```java:Test.java
if( a < b ){
  System.out.println("bが大きい")
}
System.out.println("終了")
```

```python:test.py
if a < b :
  print("bが大きい") #インデントで表現

print("終了")
```

***

### 基本的な構文4

for文

```java:Test.java
for( int i = 0; i < 3; i++ ){
  System.out.println(i)
}
System.out.println("終了")
```

```python:test.py
for i in range(3) : # iを[0,1,2]で繰り返す
  print(i)

print("終了")
```

***

### 基本的な構文5

メソッドの定義

```java:Test.java
public static int hoge(int a, int b){
  return a + b;
}
```

```python:test.py
def hoge(a,b):
  return a + b
```

***

### パッケージnumpy

ndarrayというクラスがある

- 要素に対してまとめて演算可能(すごい)

```python:test.py
tmp = [ 1, 2, 3 ] #配列の宣言
ar1 = np.ndarray(tmp) #ndarrayに変換
print(ar1) #出力:[1.0, 2.0, 3.0]

ar2 = ar1+1 #すべての要素に+1をする
print(ar2) #出力:[2.0, 3.0, 4.0]

ar3 = ar1 + ar2 #要素毎に足し算をする
print(ar3) #出力:[3.0, 5.0, 7.0]
```

***

# デモ

***

## SVM判定器のデモ

https://mybinder.org/v2/gh/takanakahiko/data_analysis_samples/master

