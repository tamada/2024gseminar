# プロジェクトの修正結果の評価

## :speaking_head: 概要

Small object programming の遵守度合いを測定するツール，[9rules](https://github.com/tamada/9rules)を作成しています．
これを使うと良でしょう．

これで指摘される項目を順番に修正したり，修正漏れがないかを確認できるようになります．
まずは，`--rough` オプションで何も指摘されないことを目指しましょう．

慣れてくれば，`--strict` オプションで何も指摘されないことを目指しましょう．
ただし，strict の場合は非常に難しく，デザインパターン（特にVisitorパターン）の理解や，
対象ソフトウェアへの理解，オブジェクト指向設計の理解も重要になってきます．

9rules自身は，strictレベルで指摘0になっていますので，どのように実装しているのか確認してみるのも良いでしょう．

## 9rulesのインストール方法

### :beer: Homebrew

```sh
brew install tamada/brew/ninerules
```

## 使い方

[9rulesのWebサイト](https://tamada.github.io/9rules/usage/)にも同じ情報を書いています．

### :runner: コマンドライン

```sh
$ 9rules --help
9rules version 1.1.0
java -jar 9rules.jar [OPTIONS] <ARGUMENTS...>

OPTIONS:
    --strict:  Strictly level check (Default).
    --general: General level check.
    --rough:   Rough level check.
    --help:    Print this message and exit.

ARGUMENTS:
    Directories include Java source files, and Java source files.
```

### :whale: Docker

以下のように入力することで，9rulesをインストールしなくてもで起動できます（ただし，[Docker](https://www.docker.com)のインストールは必要です）．

```sh
docker run --rm -v $PWD:/home/ninerules tamada/9rules:latest [OPTIONS] <ARGUMENTS...>
```

#### 実行例

```sh
$ docker run --rm -v $PWD:/home/ninerules tamada/9rules:latest --help
9rules version 1.1.0
java -jar 9rules.jar [OPTIONS] <ARGUMENTS...>

OPTIONS:
    --strict:  Strictly level check (Default).
    --general: General level check.
    --rough:   Rough level check.
    --help:    Print this message and exit.

ARGUMENTS:
    Directories include Java source files, and Java source files.
```

