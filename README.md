# unidic_ma_factory
公開版の解析用Unidic（UniDicMA）を作るためのスクリプト群。

CUI専用です。

ph0から8まで順に適用していきます。

所外から所内の様子を見たい人や（透明化）、所内での引継ぎ目的で向け公開しています。

（いままでそういったマニュアルがなかったので）

# 使い方
## 事前準備

解析用 UniDic 3.0 系からはパッケージ中にsqlというディレクトリ（フォルダ）が追加されています。

これは国語研所内のコーパスと短単位を全て管理する大規模なデータベースから、
当該の解析用UniDicの作成を行うために必要な部分（コーパス、語彙）を抽出するためのSQLファイルです。

抽出されたファイルは文字コードUTF-16なので、事前にnkfコマンドなどでUTF-8に変換します。

また上述のSQLを使って抽出すると、タブ区切り、各行の要素にはコロン（:）を前に置いた名前付きのtsvになります(.ntsv)。

仮にここでは、corpus.ntsv、lex.ntsv と呼ぶことにしましょう。

![ntsv_img](https://raw.githubusercontent.com/teru-oka-1933/unidic_ma_factory/master/img/ntsv.png "ntsv_img")

## ph0_sampling_test_data.py

このスクリプトでは、辞書の性能評価に使うコーパスをcorpus.ntsvから選びます。

評価はcorpus.ntsvからファイル単位で１割ずつ選んでいきます。

語彙素、語形、出現形、語種をチェックし、メジャーな語（短単位）で構成されているファイル～マイナーな短単位を多く含むファイルまで、
まんべんなく選択するクラスタリング手法を組み込んでいます。

入力はcorpus.ntsv、出力はディレクトリを指定します。
指定したディレクトリに、訓練用のファイル、評価用のファイル群、訓練用ファイル名一覧、評価用のファイル名一覧が作成されます。

後者2つは解析用UniDicにパッケージングして公開しています。

## ph1_preprocess4ntsv_train_corpus.py

このスクリプトでは学習用コーパスに含まれる学習に不都合な文を除去します。

## ph2_ntsv_corpus2mecab.py

このスクリプトでは

## ph3_ntsv_lex2csv.py

このスクリプトでは

## ph4_train_dic.py

このスクリプトでは


## ph5_compression_matrix.py

このスクリプトでは

## ph6_add_nfkc_entry4lex_csv.py

このスクリプトでは

## ph7_evaluation.py

このスクリプトでは

## ph8_count_suw.py

このスクリプトでは
