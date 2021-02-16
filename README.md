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

![ntsv_img](https://raw.githubusercontent.com/teru-oka-1933/unidic_ma_factory/master/img/ntsv.png "ntsv_img")

## ph0_sampling_test_data.py

これは
