GNU GLOBAL を秀丸エディタで使用するためのマクロ
=============

C/C++で「関数が呼ばれている位置」を一覧表示することが出来ます。「定義されている位置」ではなく「呼ばれている位置」です。
  ctags      関数が定義されている位置。
  GNU GLOBAL 関数が呼ばれている位置。

### このマクロの特徴
- メニューからglobalの動作を選択します。
- 検索結果は秀丸のgrepと同じ形式で出力するのでタグジャンプが可能です。

### マクロのインストールと環境設定
全ファイルを秀丸のスクリプトディレクトリにコピーしてください。

＊gtags_config.iniの設定を行って下さい
    ・GNU GLOBALへのパスを設定します。
        (例)
        >global=C:\glo593wb\bin\global.exe
        >gtags=C:\glo593wb\bin\gtags.exe

＊複数パス、複数ドライブから検索したい場合
    gtags_config.iniのSearchセクションを編集してください。
    開発中のアプリとライブラリが別ドライブにあるときに使うと便利です。

### ファイル構成
|ファイル名|説明|
|:---|:---|
|doc/readme.pdf|使い方の詳細です|
|gtags_jump.mac|マクロ本体|
|gtags_wrapper.mac|おまけマクロ|
|gtags_config.ini|設定ファイル|

### 動作環境
- 秀丸エディタ ver8以降
- でんがくDLL

### 連絡先
http://d.hatena.ne.jp/ohtorii/
https://twitter.com/ohtorii
