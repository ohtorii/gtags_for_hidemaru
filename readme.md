GNU GLOBAL を秀丸エディタで使用するためのマクロ
=============
![example](https://github.com/ohtorii/gtags_for_hidemaru/blob/master/hidemaru.png)

C/C++で「関数が呼ばれている位置」を一覧表示することが出来ます。「定義されている位置」ではなく「呼ばれている位置」です。
  ctags      関数が定義されている位置。
  GNU GLOBAL 関数が呼ばれている位置。

# このマクロの特徴
- メニューからglobalの動作を選択します。
- 検索結果は秀丸のgrepと同じ形式で出力するので、秀丸エディタの標準機能を使ってタグジャンプが可能です。

# マクロのインストール
全ファイルを秀丸のスクリプトディレクトリにコピーしてください。

# カスタマイズ
同梱の`gtags_config.ini`ファイルを編集することで、各自の環境に応じたカスタマイズが可能です。

###必須のカスタマイズ
各自の環境に合わせてGNU GLOBALへのパスを設定して下さい
```
global=C:\glo593wb\bin\global.exe
gtags=C:\glo593wb\bin\gtags.exe
```
詳細はファイル中のコメントを参照して下さい。

### タグファイルを複数のフォルダから検索したい場合は？
gtags_config.iniの`Searchセクション`を編集してください、開発中のアプリとライブラリが別フォルダ・別ドライブにあるときに使うと便利です。

# ファイル構成
|ファイル名|説明|
|:---|:---|
|doc/readme.pdf|使い方の詳細です|
|gtags_jump.mac|タグジャンプを行うマクロ（マクロ本体）|
|gtags_wrapper.mac|タグファイルの作成を補助するマクロ（おまけマクロ）|
|gtags_config.ini|設定ファイル|

# 動作環境
- 秀丸エディタ ver8以降
- でんがくDLL

# 更新履歴
### 2018/09/28 ver1.1.0
gtags_wrapper.macの改良
- ダイアログに”現在のフォルダを設定”するボタンを追加した。
- ダイアログのタイトルにバージョン番号を追加した。
### 2011/05/21 ver1.0.0
公開
  
# 連絡先
<http://d.hatena.ne.jp/ohtorii/>　<br>
<https://twitter.com/ohtorii>
