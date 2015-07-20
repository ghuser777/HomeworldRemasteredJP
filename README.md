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

### 翻訳する

\jpフォルダ以降にあるDATファイル内の英文を日本語に翻訳する。DATファイルはShift_JIS（CP932）で保存する。

### Homeworldの起動方法

準備はここまで、後はゲームの起動設定（それかLauncher.exeの起動オプション）に
`" -moddatapath translation -locale jp"`
を指定して実行すればOK。

※起動設定はSteamで、Homeworld Remasteredのプロパティ→一般タブ→起動設定...で設定できる。




## 共通ファイル

### 着手
* events.dat
* fontmap.lua

### 未着手（未確認）
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
* ミッション 04 完了
* ミッション 05 完了
* ミッション 06 完了
* ミッション 07 完了
* ミッション 08 完了
* ミッション 09 完了
* ミッション 10
* ミッション 11
* ミッション 12
* ミッション 13
* ミッション 14
* ミッション 15
* ミッション 16
* エクストラミッション Raider Retreat




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




## おおまかな用語の統一
* おおまかな用語統一案。ただし文脈により適切な言い回しがあれば変更可。
* 艦船名・地名・人名など固有名詞は「サルベージコルベット」「クライオトレイ」などとカタカナで表記する。
* 初めて出現する固有名詞や用語は「クライオトレイ(CryoTray)」のように括弧書きで英単語も併記する。その際に、英文字列の空白は削除する（Cryo Tray→CryoTray）。ワードラップにより空白以降が強制改行されてしまうため。
* また、馴染みがなく意味がわからないカタカナ語の場合は、初出のときに括弧書きで説明を付ける。例：「クライオ(冷凍睡眠)トレイ(CryoTray)」。※この場合Cryoの直訳は「冷凍睡眠」ではないがゲーム内容にそって意訳してる。
* ただし、○○strings.datでは艦船名等を英文字のまま記述する（「SalvageCorvetteを建造する」など）。カタカナにすると長すぎて画面表示が切れてしまうため。また、ビルドマネージャーやリサーチマネージャーの英文字艦船名表記と合わせるため。
* 以降の「※直訳:」は参考情報。
* カラン・スジェットは「私達」。それ以外は「我々」。
* 外来語の語尾を伸ばす。センサ、コントローラ → センサー、コントローラー。
* できる：動詞・副詞の場合「できる」。～できる、できるだけ。
* 出来る：名詞の場合「出来」。上出来、出来事。
* ください： （命令）～をしてください。
* 下さい： （物を）～を下さい。
* 全角の「？」を使うと文字化けすることがあるので半角の「?」にする。

### 用語
* Asteroid	アステロイド
* Asteroid fields	アステロイド地帯
* Build	建造（艦船）、建設（施設）
* Capture	捕獲
* Construction	建造（艦船）、建設（施設）
* Collection, Collect	集める、収集
* Deploy	配備、展開
* Drone	ドローン
* Enemy forces	敵軍、敵部隊
* Enemy ships	敵船
* Enemy units	敵部隊
* Enemy vessels	敵船
* Formation	フォーメーション
* Harvest	収集
* Hostiles	敵対者、敵対する、敵
* Hostile ships	敵対船、敵対する船、敵船
* Hyperspace	ハイパースペース
* Production	生産
* Objectives	目的
* Research	研究
* Resource	資源
* Salvage	サルベージ、回収
* Ship	船、艦艇
* Tactics	戦術
* Target	目標
* Trial	訓練、テスト
* Vessel	船、艦艇

### 固有名詞
なるべく元の発音に近いようにカタカナ化しています。  
* Bentusi	ベントゥージ
* Guidestone	ガイドストーン
* Hiigara	ヒガーラ
* Kadesh	カデッシュ
* Karan S'jet	カラン・スジェット
* Khar-Selim	カー・セリム
* Khar-Toba	カー・トバ
* Kharak	カァラーク
* Kharak System	カァラーク星系
* Taiidan	タイダーン
* Taiidan Empire	タイダーン帝国
* Turanic Raiders	トゥラニックレイダース

### 艦船・施設
* Bomber	ボマー	※直訳:爆撃機
* Capital Ship	キャピタルシップ	※直訳:主力艦
* Carrier	キャリアー	※直訳:空母
* Cruiser	クルーザー	※直訳:巡洋艦
* Cryo Tray	クライオトレイ	※冷凍睡眠トレイ	※直訳:低温/冷凍トレー
* Defender	ディフェンダー	
* Destroyer	デストロイヤー	※直訳:駆逐艦
* Fighter	ファイター。文脈により「戦闘機」
* Frigate	フリゲート
* Interceptor	インターセプター	※直訳:迎撃機
* Mothership	マザーシップ	※直訳:母船
* Research Ship	リサーチシップ	※直訳:研究船
* Resource Collecter	リソースコレクター
* Resource Controller	リソースコントローラー
* Salvage Corvette	サルベージコルベット
* Scout	スカウト	※直訳:偵察機
* Scaffold	スカフォルド	※直訳:足場
* Strikecraft	ストライククラフト
* Torpedo Frigate	トーピードフリゲート	※直訳:魚雷/水雷フリゲート艦

