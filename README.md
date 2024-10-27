# 2024年度 秋学期 先端情報学セミナーD

このページは，先端情報学セミナーDの玉田担当分（2024-10-31 (Thu), 2024-11-09 (Sat)）のページです．

## :speaking_head: 目的

リファクタリングを通じて，バージョン管理システム（git）の使い方，
そして，スモールオブジェクトプログラミングの考え方に触れる．

## やること

* 次に挙げるプロジェクトのうちの一つを選択し，リファクタリングしてください．
  * https://github.com/igakilab/redfantasy
  * https://github.com/igakilab/KGO
  * https://github.com/igakilab/MonsterPoker
  * https://github.com/igakilab/monsterzoo
  * これらのプロジェクトは，わざとオブジェクト指向的にイケていないように作られています．
* 提出はGitHub上のプロジェクトとし，そのプロジェクトのURLを[Moodleの課題](https://cclms.kyoto-su.ac.jp/mod/assign/view.php?id=136426)に記入してください．
* 締め切り　2024-11-16 (Sat) 13:15
  * 次回のセミナー開始時間まで．

### 補足事項

３人までのグループで取り組んでも構いません．
その場合，以下の点に注意してください．

* [Moodleの課題](https://cclms.kyoto-su.ac.jp/mod/assign/view.php?id=136426)にはプロジェクトのURLと各人のGitHubでのユーザIDも明記してください．
* 誰がどの部分を担当したのか，プルリクエストやIssueなどで明確にしてください．

### 手順

* [プロジェクトを手元にダウンロードする](https://github.com/tamada/2024gseminar/blob/main/notes/download.md)
* [プロジェクトを変更・提出する](https://github.com/tamada/2024gseminar/blob/main/notes/update.md)
* [プロジェクトの修正の方向性](https://github.com/tamada/2024gseminar/blob/main/notes/update_policy.md)
* [プロジェクトの修正結果の評価](https://github.com/tamada/2024gseminar/blob/main/notes/evaluation.md)

### サンプルプロジェクト

* [fizzbuzz](https://github.com/tamada/fizzbuzz)
* [triangle](https://github.com/tamada/triangle)

以下のプロジェクトのひな形は，`src` 以下に何もない状態です．
`src/main` にプロダクトコード，`src/test` にテストコードを配置して `./gradlew build` を実行するとテストが実施され，カバレッジレポート（`build/reports/jacoco/test/html`），SpotBugsのレポート（`build/reports/spotbugs/main.html`）などが出力されます．
ご自由に利用してください．

* [プロジェクトの雛形](https://github.com/tamada/gradle_template)

## About

* このページは[玉田](https://tamadalab.github.io)が作成しました．
* リファクタリング対象のプロジェクトは大阪工業大学の[井垣先生](https://igakilab.github.io)にご提供いただきました．
* [![クリエイティブ・コモンズ 表示 - 非営利 - 継承 4.0 国際 ライセンス](https://github.com/tamada/2022gseminar/blob/main/images/license.png)](http://creativecommons.org/licenses/by-nc-sa/4.0/)

## 参考

* [Gitでのバージョン コントロールの概要](https://learn.microsoft.com/ja-jp/training/paths/intro-to-vc-git/)
* [オブジェクト指向は単なる【整理術】だよ](https://qiita.com/br_branch/items/2aa9859d4da41991bbb7) (Qiita)
* [うまくメソッド名を付けるための参考情報](https://qiita.com/KeithYokoma/items/2193cf79ba76563e3db6) (Qiita)
* [正しい名前をつけることが大切な理由](https://qiita.com/tutinoco/items/85641c0819d813186f9d) (Qiita)
* [オブジェクト指向と10年戦ってわかったこと](https://qiita.com/tutinoco/items/6952b01e5fc38914ec4e) (Qiita)
