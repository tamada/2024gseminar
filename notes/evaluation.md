# プロジェクトの修正結果の評価

## :speaking_head: 概要

Small object programming の遵守度合いを測定するツール，[9rules](https://github.com/tamada/9rules)がある．
これを使うと良でしょう．

これで指摘される項目を順番に修正したり，修正漏れがないかを確認できるようになります．

## 9rulesのインストール方法

### :beer: Homebrew

```sh
brew install tamada/brew/ninerules
```

## 使い方

[9rulesのWebサイト](https://tamada.github.io/9rules/usage/)にも同じ情報を書いている．

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

以下のように入力することで，9rulesをインストールしなくてもで起動できる（ただし，[Docker](https://www.docker.com)のインストールは必要）．

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

