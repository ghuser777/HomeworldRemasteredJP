# HomeworldRemasteredJP
Homeworld Remasteredの日本語化作業




## 日本語化の仕方

コマンドライン作業の知識などが必要なので、ちょっとめんどうで時間がかかります。  

とりあえず日本語表示を試すだけなら、有志の方が7月25日時点のbigファイルを作成してくれたので、そちらを利用すると簡単に確認できます。

・【宇宙】 Homeworld 総合スレ 【戦略】 Stage 10 [転載禁止]©2ch.net
http://anago.2ch.net/test/read.cgi/game/1425371135/187。


### 日本語フォントをダウンロードする。

「HomeWorld 攻略Wiki」からRemastered用の日本語フォントをダウンロードする。
http://homeworld.wiki.fc2.com/wiki/MOD


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
※なお、Update○○.bigは暗号化されていないかも？dropBigHere.batにドロップして復号されなければ暗号化されていないので、Archive.exeによるファイルの展開だけでOKです。

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

（これは必要ないかも？）上記fontmap.luaに`FontMap1920 =`のブロックを増やす（テキストをコピペして1920に書き換える）。


### 翻訳する

\jpフォルダ以降にあるDATファイル内の英文を日本語に翻訳する。DATファイルはShift_JIS（CP932）で保存する。

現在作業中の翻訳の大本は「Hiigara Chronicles」さんのものを使わせて頂いています。

Hiigara Chronicles [Rev.A since 2005/3/13]  
http://www.geocities.jp/hiigara_chronicle/index.html

その他には、

Encyclopedia Hiigara  
http://homeworld.wikia.com/wiki/Main_Page

Google翻訳  
https://translate.google.co.jp/

エキサイト翻訳  
http://www.excite.co.jp/world/

英和辞典・和英辞典 - Weblio辞書  
http://ejje.weblio.jp/

各種辞典・英語文法事例・日本語文法事例サイト、Wikipedia、米国のWikipediaや固有名詞・熟語・慣用句等のソース(ネタ元/意味)などがわかる外国サイトなどを元に作業をしています。


### Homeworldの起動方法

準備はここまで、後はゲームの起動設定（それかLauncher.exeの起動オプション）に  
`" -moddatapath translation -locale jp"`  
を指定して実行すればOK。他のMODも動く。

※起動設定はSteamの、Homeworld Remasteredのプロパティ→一般タブ→起動設定...で設定できる。




## 共通ファイル


### 着手

* events.dat
* fontmap.lua
* hw1buildresearch.dat 作業中


### 未着手（未確認）

* ati.dat
* buildresearch.dat
* delete.dat
* engine.dat
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
* ミッション 10 完了
* ミッション 11 完了
* ミッション 12 完了
* ミッション 13 完了
* ミッション 14 作業中
* ミッション 15 作業中
* ミッション 16 作業中
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
* また、馴染みがなく意味がわからないカタカナ語の場合は、初出のときに括弧書きで説明を付ける。例：「クライオ(冷凍睡眠)トレイ(CryoTray)」。 ※この場合Cryoの直訳は「冷凍睡眠」ではないがゲーム内容にそって意訳してる。
* ただし、○○strings.datでは艦船名等を英文字のまま記述する（「SalvageCorvetteを建造する」など）。カタカナにすると長すぎて画面表示が切れてしまうため。また、ビルドマネージャーやリサーチマネージャーの英文字艦船名表記と合わせるため。
* ○○strings.datのミッションタイトルは、日本語訳＋元の英文を山括弧で囲む。  
 例：`＜カァラーク星系(KHARAK SYSTEM)＞`
* カラン・スジェットと使節は「私達」。それ以外は「我々」。
* ベントゥージがこちらを呼ぶ場合「あなた方」。エルソン艦長は「あなた達」。敵対勢力がこちらを呼ぶ場合「お前達」。
* 味方側のセリフ、敵対勢力内での無線通信などは「です・ます調」。ベントゥージや敵対勢力がこちら側に話しかける場合は「だ・である調」。
* 出来る／できる： 動詞・副詞の場合「できる」（～できる、できるだけ）。名詞の場合「出来」（上出来、出来事）。
* 下さい／ください： （命令）～をしてください。（物を）～を下さい。
* 外来語の語尾を伸ばす。センサ、コントローラ → センサー、コントローラー。
* 全角の「？」を使うと文字化けすることがあるので半角の「?」にする。
* 以降の「※直訳:」は参考情報。


### 用語

* Asteroid	アステロイド、アステロイド群
* Asteroid fields	アステロイド地帯
* Build	建造（艦船）、建設（施設）
* Capture	捕獲
* Construction	建造（艦船）、建設（施設）
* Collection, Collect	集める、収集
* Deploy	配備、展開
* Drone	ドローン
* Enemy fleet	敵艦隊
* Enemy forces	敵部隊、敵軍
* Enemy ships	敵艦
* Enemy units	敵部隊
* Enemy vessels	敵艦
* Formation	フォーメーション
* Group Captain	大佐	※イギリス空軍の階級で大佐
* Harvest	収集
* Hostiles	敵対者、敵対する、敵
* Hostile ships	敵対艦、敵対する船、敵艦
* Hyperspace	ハイパースペース
* Production	生産
* Objectives	目的
* Research	研究
* Resource	資源
* Salvage	サルベージ、回収
* Squadron	隊、戦隊、艦隊。Squadron of Scout:スカウトの戦隊。Scout squadron:スカウト隊。
* Ship	艦、船、艦艇
* Tactics	戦術
* Target	目標
* Trial	訓練、テスト
* Vessel	艦、船、艦艇


### 固有名詞

なるべく元の発音に近いようにカタカナ化しています。 元ネタについては調査が甘く間違っている可能性もあります。 
* Bentusi	ベントゥージ
* BRIDGE OF SIGHS	ため息橋  
※元ネタ？：16世紀に架けられたヴェネツィアの橋の1つ。観光名所。大理石で造られた橋には覆いがあり、石でできた格子の付いた窓が付けられている。渡った先は宮殿の尋問室と牢獄へと続く。  
ため息橋という名前は、独房に入れられる前に窓の外からヴェネツィアの美しい景色を見られるのは最後であるというので囚人がため息をつくというところから、19世紀にジョージ・バイロンが名づけた。
* CHAPEL PERILOUS	危険な礼拝堂  
※元ネタ：チャペル・ペララス。15世紀後半にウェールズ人のサー・トマス・マロリーによって書かれた中世におけるアーサー王文学の集大成ともいえる長編作品『アーサー王物語』の中に登場する。  
魔女ヘラヴィーサは、円卓の騎士ランスロットを誘惑するためにランスロットにたいする偽の自分の愛と幻の礼拝堂を魔法で作り上げたが、幻は見破られ愛は拒絶された。その後、自分の作り上げた偽の愛にとらわれ拒絶されたことにより自殺してしまう。  
アメリカ合衆国の小説家・神秘主義思想家のロバート・アントン・ウィルソンは、自著コスミック・トリガーの中で「オカルト陰謀論をちゃんと学ぼうとした人間が、逆にオカルトに嵌ってしまうことがある現象を仲間内で「危険な礼拝堂(チャペル・ペララス)」と呼んでいる」（要約）と語っており、ミイラ取りがミイラになってしまうような物語設定を「危険な礼拝堂(チャペル・ペララス)」と呼ぶことがあるようだ。  
本ゲーム内では、巨大アステロイドがマザーシップに向かってくるミッションのタイトル。一歩間違えばタイダーン艦隊自身が巨大アステロイドに巻き込まれてしまうような状況から「危険な礼拝堂(チャペル・ペララス)」というタイトルになっているのかもしれない。
* DIAMOND SHOALS	ダイヤモンドショールズ  
※元ネタ：アメリカ合衆国ノースカロライナ州東端に突き出たアウターバンクスと呼ばれる砂州の中の、ハッテラス島ハッテラス岬沖のDiamond Shoals（ダイアモンド砂州）と呼ばれる場所は、特に航海の難所として知られている。
* Guidestone	ガイドストーン
* Hiigara	ヒガーラ
* Kadesh	カデッシュ  
※元ネタ：「聖なるもの」「分離」を意味するヘブライ語。旧約聖書において、エジプトを脱出したモーセ率いるイスラエルの人々が、続く38年間をカデシュもしくはカデシュ・バルネアと呼ばれる地で過ごしたことが暗に語られている。  
なお、古代のシリアにあった都市国家カデシュとは位置が微妙に違う。関連は不明。
* Kapella	カペラ
* Karan S'jet	カラン・スジェット
* Karos	カロス
* Khar-Selim	カー・セリム
* Khar-Toba	カー・トバ
* Kharak	カァラーク
* Kharak System	カァラーク星系
* Kushan	クーシャン
* SHINING HINTERLANDS	シャイニングヒンターランド  
※Encyclopedia Hiigaraによるとこの地名の元ネタは不明であるが、銀河系中心部から少し離れたヒンターランド(後背地)が、輝く銀河中心部を見る位置にあるためまさに適切な地名ではないかとのこと。
* Taiidan	タイダーン
* Taiidan Empire	タイダーン帝国
* TENHAUSER GATE	タンホイザーゲート  
※元ネタ：映画ブレードランナーの有名なセリフの中にでてくる。タンホイザーゲートはSFネタとして使われアニメ「トップをねらえ!」にもでてくる。
* The First Time	「始まりの時代(TheFirstTime)」
* The Unbound	「解き放たれし者(TheUnbound)」
* Turanic Raiders	トゥラニックレイダース


### 艦船・施設

* Bomber	ボマー	※直訳:爆撃機
* Capital Ship	キャピタルシップ	※直訳:主力艦
* Carrier	キャリアー	※直訳:空母
* Cloaked Fighter	クロークドファイター
* Cruiser	クルーザー	※直訳:巡洋艦
* Cryo Tray	クライオトレイ	※冷凍睡眠トレイ	※直訳:低温/冷凍トレー
* Defender	ディフェンダー	
* Destroyer	デストロイヤー	※直訳:駆逐艦
* Fighter	ファイター。文脈により「戦闘機」
* Frigate	フリゲート
* Interceptor	インターセプター	※直訳:迎撃機
* Missile Destroyer	ミサイルデストロイヤー	※直訳:ミサイル駆逐艦
* Mothership	マザーシップ	※直訳:母船
* Proximity Sensor	プロキシミティセンサー	※直訳:近接センサー
* Research Ship	リサーチシップ	※直訳:研究船
* Resource Collecter	リソースコレクター
* Resource Controller	リソースコントローラー
* Salvage Corvette	サルベージコルベット
* Scaffold	スカフォルド	※直訳:足場
* Scout	スカウト	※直訳:偵察機
* Strikecraft	ストライククラフト
* Torpedo Frigate	トーピードフリゲート	※直訳:魚雷/水雷フリゲート艦
