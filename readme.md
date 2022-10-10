# GNU GLOBAL を秀丸エディタで使用するためのマクロ

![GitHub release](https://img.shields.io/github/release/ohtorii/gtags_for_hidemaru.svg)
![Maintenance](https://img.shields.io/maintenance/yes/2020.svg)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# このマクロの特徴

このマクロは[GNU GLOBAL(gtags)](https://www.tamacom.com/global-j.html)を使用して「関数・変数が呼ばれているソースコード位置」を秀丸エディタで一覧表示することが出来ます。

# 動作イメージ
- カーソルを調べたい単語の上に置いてから`gtags_jump.mac`マクロを実行するとメニューが開きます。
- メニューからgtagsの動作を選択します。
- 検索結果は秀丸のgrepと同じ形式で出力するので、秀丸エディタの標準機能を使ってタグジャンプが可能です。

## gtags_jump.mac（タグジャンプを行う本体マクロ）

![example](images/gtags_jump.gif)

## gtags_wrapper.mac (タグファイル生成をサポートするGUIマクロ)

![example](images/gtags_wrapper.gif)


# マクロの導入方法

このようにコピーして下さい。

	└─hidemaru-macrodir
	    └─gtags_for_hidemaru
	        ├─doc
	        ├─images
	        └─macro
	            ├─gtags_config.ini
	            ├─gtags_jump.mac
	            └─gtags_wrapper.mac
	
- gtags_jump.mac マクロに任意のショートカットキーを割り当ててご使用下さい。
- gtags_wrapper.mac は*おまけのマクロ*です、後述の説明を読んで必要な方だけご使用下さい。

## ファイル構成

|ファイル名|説明|
|:---|:---|
|macro/gtags_jump.mac|タグジャンプを行うマクロ（マクロ本体）|
|macro/gtags_wrapper.mac|タグファイルの作成を補助するGUIマクロ（おまけのマクロ）|
|macro/gtags_config.ini|設定ファイル|
|doc/readme.pdf|使い方の詳細です|

# カスタマイズ

同梱の`gtags_config.ini`ファイルを編集することで、各自の環境に応じたカスタマイズが可能です。

```ini
;
; ShiftJIS
;

[Path]
;===============================
;win32
;===============================
;global,gtagsへのパス

global=C:\glo662wb\bin\global.exe
gtags=C:\glo662wb\bin\gtags.exe

;global=C:\glo593wb\bin\global.exe
;gtags=C:\glo593wb\bin\gtags.exe

;環境変数が利用できます
;global=%HOMEDRIVE%%HOMEPATH%\gtags\bin\global.exe
;gtags=%HOMEDRIVE%%HOMEPATH%\gtags\bin\gtags.exe

;===============================
;MSYS2
;===============================
;global=C:\tools\msys64\usr\bin\global.exe
;gtags=C:\tools\msys64\usr\bin\gtags

;===============================
;cygwin
;===============================
;gtags=C:\cygwin\usr\local\bin\global.exe
;gtags=C:\cygwin\usr\local\bin\gtags.exe


[Search]
;親フォルダのタグファイルからジャンプ先が見つからない場合は、下記パスのタグファイルから再検索する
;0-9まで指定可能（環境変数が利用できます）
;Path0=D:\project\my_lib\trunk
;Path1=K:\libs\boost\
;Path2=%USERPROFILE%\my_lib

[Dialog]
;ダイアログに設定した値はマクロ終了後にこのセクションへ書き込まれます

dir=C:\your_apps_folder
arg=-v -w

;ファイル生成に Exuberant Ctags を利用する。（詳細は各自で調べて下さい :-P）
;arg=--gtagslabel=pygments

;設定ファイルを指定する(環境変数が利用できます)
;arg=--gtagsconf %HOMEDRIVE%%HOMEPATH%\gtags.conf
```

## 必須のカスタマイズ

各自の環境に合わせてGNU GLOBALの実行ファイルのパスを設定して下さい。
```
global=C:\glo593wb\bin\global.exe
gtags=C:\glo593wb\bin\gtags.exe
```
詳細はファイル中のコメントを参照して下さい。

## タグファイルを複数フォルダから検索する設定

gtags_config.iniの`Searchセクション`を編集してください、開発中のアプリとライブラリが別フォルダ・別ドライブにあるときに使うと便利です。


# 動作環境

- 秀丸エディタ ver8以降(32bit版、または、64bit版)
- [田楽DLL 32bit](http://www.ceres.dti.ne.jp/~sugiura/hidemaru/macros/dgserver/#download64)、または、[田楽DLL 64bit](http://htom.in.coocan.jp/macro/macro_dll.html#label-5)
- [GNU GLOBAL](https://www.tamacom.com/global-j.html)

# バージョン番号のルール

バージョン番号の表記方法

バージョン番号は version 1.2.3 のように表記され、それぞれ major.minor.revision を表します。

|番号|説明|
|:--:|:--:|
|major|互換性が失われる大きな変更を表します|
|minor|機能追加のように互換性のある更新を表します|
|revision|バグ修正のように機能そのものに変化が無い軽微な更新を表します|

# ダウンロード

こちらから動作確認済みのアーカイブをダウンロードして下さい。<br>
https://github.com/ohtorii/gtags_for_hidemaru/releases

*注意*
masterブランチを取得しても多分動作しないです。<br>
一人で開発しているのでブランチを作らずに気楽に開発してます。（仕事じゃないしね😉）

# トラブル事例

## マクロを実行しても関数・変数が呼ばれているソースコード位置が表示されない
- [GNU GLOBAL(gtags)](https://www.tamacom.com/global-j.html)がコマンドプロンプトで動作するかどうかを確認して原因の切り分けを行って下さい。
- コマンドプロンプトで期待したとおりに動作するように設定を済ませてからこのマクロを使用して下さい、。

# 作者に感謝
- [田楽DLL 32bit](http://www.ceres.dti.ne.jp/~sugiura/hidemaru/macros/dgserver/#download64)
- [田楽DLL 64bit](http://htom.in.coocan.jp/macro/macro_dll.html#label-5)
- [GNU GLOBAL](https://www.tamacom.com/global-j.html)

# 連絡先
<http://d.hatena.ne.jp/ohtorii/> <br>
<https://twitter.com/ohtorii> <br>
<https://github.com/ohtorii/gtags_for_hidemaru>
