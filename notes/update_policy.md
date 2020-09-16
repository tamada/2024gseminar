# プロジェクトの修正の方向性

## :speaking_head: 概要

次の方針に従って修正を行っていきましょう．

* メソッドに分割しましょう．
* クラスに分割しましょう．
* 同じようなコード断片（コードクローン）はメソッドにまとめましょう．
* `Collection`（`List`，`Map`，`Set`）を使いましょう．
* `Stream` を使いましょう．

## 似通ったコード断片（コードクローン）はメソッドにまとめましょう．

* 似通ったコード断片はまとめて一つのメソッドにしましょう．
    * コードクローンは基本的に避けるべきものです．
        * 許容されるコードクローンは自動的に生成されたものです．

## メソッドに分割しましょう．

* メソッドの行数が5行を超えると分割する対象と考えましょう．
* 特に，ネストが２段階より深くなるとメソッドに分けましょう．

## クラスに分割しましょう．

* 対象プロジェクトの README.md に書かれている仕様をよく読みましょう．
* 仕様の中に書かれている名詞がクラスの候補になります．
* 関連するメソッドを集めましょう．
* getter/setter は避けましょう．
    * [Java Beans の大罪 〜 getter/setter を捨てて美しきオブジェクトの世界で生きよ〜](https://blog1.mammb.com/entry/2019/12/06/090000)

## `Collection`を使いましょう．

* 配列を使っている箇所は，`List`に置き換えましょう．

## `Stream` を使いましょう．

* できれば，`for` 文を Stream を使った処理に置き換えましょう．
    * [Java8 ラムダとStreamAPIを理解する](https://qiita.com/gosshys/items/cde9e5921cfc926a5c00) (Qiita)
    * [Java Stream APIをいまさら入門](https://qiita.com/takumi-n/items/369dd3fcb9ccb8fcfa44) (Qiita)

## `Stream`への置き換え例

### 数値の列挙

#### 従来の書き方

```java
for(int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

#### Streamを使った書き方

以下のプログラムは`0`〜`10`（`10`は含まない）それぞれの値に対して，
`forEach` の中身（`value -> System.out.println(value)`）を実行します．

```java
IntStream.range(0, 10) // 
    .forEach(value -> System.out.println(value));
```

`forEach` の中身（`value -> System.out.println(value)`）は，次のプログラムの省略型です．

```java
IntStream.range(0, 10)
    .forEach(new Consumer<>() {
        public void accept(Integer value){
            System.out.println(value);
        }
    });
```

なお，`value -> System.out.println(value)` はもっと省略できて，
`System.out::println` とも書けます．

### 奇数の合計

#### 従来の書き方

```java
int sum = 0;
for(int i = 0; i < 100; i++) {
    if(i % 2 == 1) {
        sum += i;
    }
}
System.out.printf("0から100までの奇数の合計は%dです．%n", sum);
```

#### Streamを使った書き方

```java
int sum = IntStream.range(0, 100)
    .filter(value -> value % 2 == 1) // 奇数のみを取り出す．
    .sum();                          // 合計を計算する．
System.out.printf("0から100までの奇数の合計は%dです．%n", sum);
```

### 与えられたリストの奇数の合計値，偶数の合計値をそれぞれ計算する．

#### 従来の書き方

```java
public void printSumOfEvenOdd(List<Integer> list) {
    int sumOfOdds = 0;
    int sumOfEvens = 0;
    for(int i = 0; i < 100; i++) {
        if(i % 2 == 1) {
            sumOfOdds += i;
        }
        else {
            sumOfEvens += i;
        }
    }
    System.out.printf("奇数の合計は%d，偶数の合計は%dです．%n", sumOfOdds, sumOfEvens);
}
```

#### Streamを使った書き方

```java
public void printSumOfEvenOdd(List<Integer> list) {
    Predicate<Integer> predicate = (value) -> value % 2 == 1;
    int sumOfOdds = list.stream().filter(predicate)
        .collect(Collectors.reducing(0, (prev, next) -> prev + next));
    int sumOfEvens = list.stream().filter(predicate.negate())
        .collect(Collectors.reducing(0, (prev, next) -> prev + next));
    System.out.printf("奇数の合計は%d，偶数の合計は%dです．%n", sumOfOdds, sumOfEvens);
}
```

* 一つの繰り返しで両方を求めるのではなく，その都度 `Stream` を作成し求めましょう．
* ラムダ式は上記の2行目のように変数に代入可能です．
* 条件が反転する場合，`negate` で反転することを明示すると何をしているかわかりやすいでしょう．
* ただし，コードクローンができましたので，次のようにメソッドに切り出すと良いでしょう．

```java
public void printSumOfEvenOdd(List<Integer> list) {
    Predicate<Integer> predicate = (value) -> value % 2 == 1;
    int sumOfOdds = summingList(list, predicate);
    int sumOfEvens = summingList(list, predicate.negate());
    System.out.printf("奇数の合計は%d，偶数の合計は%dです．%n", sumOfOdds, sumOfEvens);
}

private int summingList(List<Integer> list, Predicate<Integer> predicate){
    return list.stream()
        .filter(predicate)
        .collect(Collectors.reducing(0, (prev, next) -> prev + next));
}
```

Streamでどのように書けば良いのかは [Issue](https://github.com/tamada/2020gseminar/issues)などで聞いてもらえればできる限りお答えします．
