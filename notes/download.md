# プロジェクトを手元にダウンロードする

## :speaking_head: 概要

ここでは，プロジェクトのソースコードを手元にダウンロードする方法について説明します．
最終的に GitHub のプロジェクトとしてアップロードする必要がありますので，次の手順でダウンロードします．

以下の説明では，玉田（[`tamada`](https://github.com/tamada)）が[MonsterPoker](https://github.com/igakilab/MonsterPoker)の修正に取り組む手順を例として説明しています．
GitHubのユーザID（`tamada`）やプロジェクト名（`MonsterPoker`）は必要に応じて読み替えてください．

1. [igakilab/MonsterPoker](https://github.com/igakilab/MonsterPoker)をforkし，`tamada/MonsterPoker`を作成する．
2. `tamada/MonsterPoker`をcloneする．
3. プロジェクトを編集・提出する．

## 1. プロジェクトをforkする．

1. [igakilab/MonsterPoker](https://github.com/igakilab/MonsterPoker)のGitHubのページを開きます．
    * ![igakilab/MonsterPokerのGitHubページ](https://github.com/tamada/2020gseminar/blob/master/images/monsterpoker_github.png)
2. GitHubのページの左上のリポジトリの名前が`igakilab/MonsterPoker`になっていることを確認しましょう．
    * ![igakilab/MonsterPokerのGitHubページ](https://github.com/tamada/2020gseminar/blob/master/images/monsterpoker_github2.png)
3. forkボタンを押し，プロジェクトをforkします（自分のリポジトリとして分岐させること）．
    * ![igakilab/MonsterPokerのGitHubページ](https://github.com/tamada/2020gseminar/blob/master/images/monsterpoker_fork.png)
4. 以下のような画面になっていればforkが完了しています．
    * ![igakilab/MonsterPokerのGitHubページ](https://github.com/tamada/2020gseminar/blob/master/images/monsterpoker_forked.png)

## 2. プロジェクトをclone（ダウンロード）する．

5. コードをダウンロードするURLをクリップボードにコピーしましょう．`code`ボタンを押し，下図のコピーアイコンをクリックしてください．
    * ![igakilab/MonsterPokerのGitHubページ](https://github.com/tamada/2020gseminar/blob/master/images/monsterpoker_clone.png)
6. ターミナルを開き，適当なディレクトリで，`git clone `と入力後，先ほどコピーしたURLをペーストしてコマンドを実行してください．これにより，リモートリポジトリの内容をローカル環境に複製（クローン）します．
    * 上の例であれば，`git clone git@github.com:tamada/MonsterPoker.git` というコマンドを実行します．
      コマンドを実行したディレクトリに `MonsterPoker` というディレクトリが作成されます．
7. 作成されたディレクトリに移動し，コンパイル，実行して実行結果を確認しましょう．
    * いずれのプロジェクトでも，同じ構造になっていますので，コンパイル，実行方法は同じです．
    * `javac -d classes src/*.java` で `classes` ディレクトリ以下にクラスファイルが作成されます．
    * `java -classpath classes Main` コマンドで実行できます．実行後の処理については，`README.md` をご覧ください．

以上の操作ができれば，[プロジェクトを編集・提出する](update.md)をご覧ください．

