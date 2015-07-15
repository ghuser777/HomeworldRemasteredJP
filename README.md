# HomeworldRemasteredJP
Homeworld Remasteredの日本語化作業




## 日本語化の仕方
「HomeWorld 攻略Wiki」からRemastered用の日本語フォントをダウンロードする。
http://homeworld.wiki.fc2.com/wiki/MOD

日本語化の仕方は上記日本語フォントのreame.txtに書いてありますが、一部誤字脱字・漏れなどがあるので、あらためて以下に書きます。

### 暗号化されたBigファイルを復号するプログラムを入手する。

・bigDecrypter.exe  
Homeworld RemastererdのDataフォルダに含まれている暗号化されたBigファイルをArchive.exeで扱える形式に復号するプログラム。  
海外有志によって作成された物で下記のサイトに有るbigDecrypter_1.4.zipが該当する。  
https://github.com/mon/bigDecrypter/releases

使い方は復号したいBigフィアルをdropBigHere.batにドロップする。  
ファイルをドロップするとドロップしたファイルと同じ場所に"<ファイル名>_decrypted"の名前で復号されたファイルが作成される。

### 復号したBigファイルを個々のファイルに展開するプログラムを入手する

bigDecrypter.exeで復号したBigファイルを個々のファイルに展開するためのプログラムツール(Archive.exe)をSteamから手に入れる。

Steamを起動して「ライブラリ」から「ツール」を選択し、一覧が表示されるので「Homeworld Remastered Toolkit」をダブルクリック又は右クリックメニューからインストールする。

Toolkitをインストールすると、Archive.exeは標準で以下のフォルダにあるはず。  
`C:\Program Files (x86)\Steam\steamapps\common\Homeworld\GBXTools\WorkshopTool`

Archive.exeの使い方は、コマンドプロンプトで以下のコマンドを実行。  
`Archive.exe -a <Bigファイル名> -e <展開先のフォルダ名>`

### 作業に必要なBigファイルを復号＆展開する

dropBigHere.batとArchive.exeを使って、Bigファイルを復号＆展開する。必要となるBigファイルは下記。  
※2015年7月4日時点。

C:\Program Files (x86)\Steam\steamapps\common\Homeworld\HomeworldRM\Data
* English.big
* EnglishHW1Campaign.big
* EnglishHW2Campaign.big
* EnglishSpeech.big
* EnglishSpeechHW1Campaign.big
* EnglishSpeechHW2Campaign.big
* HW2Campaign.big
* Music.big
* MusicHW1Campaign.big
* MusicHW2Campaign.big

C:\Program Files (x86)\Steam\steamapps\common\Homeworld\HomeworldRM\DataUpdates
* UpdateEnglish.big
* UpdateEnglishSpeech.big
* UpdateEnglishSpeechHW2Campaign.big
* UpdateMusic.big
* UpdateMusicHW1Campaign.big

### Homeworld Remasteredのフォルダに新規フォルダを作成し、必要なファイルをコピーする。

C:\Program Files (x86)\Steam\steamapps\common\Homeworld\HomeworldRMフォルダの下に、下記フォルダを作成する。
* \translation\locale\jp
* \translation\ui\font

以下Bigファイルの内容をjpフォルダにコピーする。
* English.big
* EnglishHW1Campaign.big
* EnglishHW2Campaign.big
* UpdateEnglish.big

※ファイルが重複する場合、Update○○.bigのほうを優先(上書き)する。  
※missions.luaなど、Update○○.bigと関係なく重複するファルがある場合は現時点では好きに上書きする（最終的にはちゃんと分離させる必要があるかも）。

以下Bigファイルの内容をtranslationフォルダにコピーする。
* EnglishSpeech.big
* EnglishSpeechHW1Campaign.big
* EnglishSpeechHW2Campaign.big
* Music.big
* MusicHW1Campaign.big
* MusicHW2Campaign.big
* UpdateEnglishSpeech.big
* UpdateEnglishSpeechHW2Campaign.big
* UpdateMusic.big
* UpdateMusicHW1Campaign.big

HW2Campaign.bigの\localeに有るlocaledat.luaを\translation\localeへコピーする。

日本語フォントファイルを\translation\ui\fontへコピーする。

空のテキストファイルをkeeper.txtの名前で\translationに作成する。

\translation\locale\jp\fontmap.luaを開き、フォント定義(Blender.rcfとSmallFonts7.rcf)を全て、日本語フォントのファイル名(MigMix2p.rcf)に書き換える。

\jp内のDATを翻訳してShift_JIS（CP932）で保存する。

### Homeworldの起動方法

準備はここまで、後はゲームの起動設定（それかLauncher.exeの起動オプション）に" -moddatapath translation -locale jp"を指定して実行すればOK。

※起動設定はSteamで、Homeworld Remasteredのプロパティ→一般タブ→起動設定...で設定できる。




## 共通ファイル
### 着手
* events.dat
* fontmap.lua

### 未着手
* ati.dat
* buildresearch.dat
* delete.dat
* engine.dat
* hw1buildresearch.dat
* hw1ships.dat
* leveldesc.dat
* leveldeschw2.dat
* resource.dat
* ships.dat
* ui.dat

## Homeworld Remastered チュートリアル
* チュートリアル 01 完了
* チュートリアル 02 完了
* チュートリアル 03 完了

## Homeworld 1 Remastered
* ミッション 01 完了
* ミッション 02 完了
* ミッション 03 完了
* ミッション 04
* ミッション 05
* ミッション 06
* ミッション 07
* ミッション 08
* ミッション 09
* ミッション 10
* ミッション 11
* ミッション 12
* ミッション 13
* ミッション 14
* ミッション 15
* ミッション 16

## Homeworld 2 Remastered
* ミッション 01
* ミッション 02
* ミッション 03
* ミッション 04
* ミッション 05
* ミッション 06
* ミッション 07
* ミッション 08
* ミッション 09
* ミッション 10
* ミッション 11
* ミッション 12
* ミッション 13
* ミッション 14
* ミッション 15

## Multiplayer
？

