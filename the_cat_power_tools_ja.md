# OmegaT - The CAT パワーツール
## 技と術で翻訳プロジェクトをサバイバル!


###### tags: `OmegaT`, `Translation`, `Tutorial`, `intermediate`


![Cover](https://i.imgur.com/xDqSCct.gif)
Serval wild cat in Africa, ClipArt ETC is copyright ©2020 by the University of South Florida [![Clipart ETC: Animals Menu](https://fcit.usf.edu/home/promo/ca/images/animals88x31.gif)](https://etc.usf.edu/clipart/sitemap/animals.htm)

## Copyright

Copyright (c) 2020 Hiroshi Miura

Permission is granted to copy, distribute and/or modify this document under the terms of the GNU Free Documentation License,
Version 1.3 or any later version published by the Free Software Foundation; with no Invariant Sections,
no Front-Cover Texts, and no Back-Cover Texts. A copy of the license is included in the section entitled "GNU Free Document License".

Cover illustration is from  the University of South Florida,
[ClipArt ETC](https://etc.usf.edu/clipart/) in grant of ClipArt ETC Free Classroom License.

Last update: September 2020  \
Refer to OmegaT version: 5.4.0

スクリーンショトは、OmegaT version 5.4.0 on Windows 10 Enterprise(Build 19041)です。

OmegaTの開発が速いため、最新版では、画面がことなる可能性があります。


# 1 はじめに

このチュートリアルは、[CATビギナーのためのOmegaT入門](/@omegat/rJU6Pl5mw)を習得しおえたくらいの中級レベルの方むけに、OmegaTを効果的につかいこなす高度なテクニックを解説し、翻訳作業を劇的に高速にすることを目指しています。


# 2 プラグインの活用

OmegaTには、プラグインによりその機能を拡張する仕組みがそなわっています。プラグインには、様々なファイルフォーマットへの対応や、地域限定の辞書フォーマットの対応、本体にくみこまれていない機械翻訳エンジンへの対応などが存在しています。
プラグインは、OmegaTのホームページに、一覧されています。



日本語に関わる翻訳において、OmegaTの能力を活用するには、拡張機能が必要となります。

本チュートリアルでおすすめするプラグインには、次のものがあります。

* CDROM/DVD-ROM辞書対応：EPWING辞書フォーマット対応プラグイン
* TexTra機械翻訳エンジン：TexTraプラグイン
* Markdown,XLIFF対応:  Okapi filters plugin for OmegaT

## 2.1 プラグインの導入方法

プラグインは、OmegaTの配布とは別の場所で配布されています。それぞれのプラグインのホームページから入手することが必要です。

ここでは、例として[Okapi filters plugin for OmagaT](https://okapiframework.org/wiki/index.php?title=Okapi_Filters_Plugin_for_OmegaT) プラグインを導入してみましょう。
[Okapi filters for OmagaT](https://okapiframework.org/wiki/index.php?title=Okapi_Filters_Plugin_for_OmegaT) プラグインは、OmegaTが扱えるファイルフォーマットを拡張するもので、様々なファイルに対応できるようにしてくれます。特筆すべきファイルフォーマットは次のとおりです。

* Markdown(.md)
* XLIFF (.xlf .xliff)
* InDesign IDML ファイル (.idml)
* Microsoft Office(.docx)

これ以外にも、多数のフォーマットに対応しています。

### 2.1.1 Okapi filters plugin for OmagaT プラグインのダウンロード

プラグインは、Okapi Frameworkのホームページから入手できます。

プロジェクトのダウンロード専用ページを訪問してください。

https://bintray.com/okapi/Distribution/OmegaT_Plugin

![](https://i.imgur.com/Mdt73dq.png)


一般にプラグインは、OSに依存していません。左下のZIPファイルのリンクをクリックして、ダウンロードしてください。ダウンロードして展開すると、いくつかのフィアルが含まれていることがわかります。


![](https://i.imgur.com/wJx0HXZ.png)


拡張子が `.jar`のファイル、上記の例では、`okapiFiltersForOmagaT-1.8.1.40.0.jar` ファイルがプラグインの本体です。

### 2.1.2 プラグインのインストール


* TL;DR
    * Windowsの場合: `C:\Users\<username>\AppData\Roaming\OmegaT`
    * macOSの場合: `~/Library/Preferences/OmegaT/plugins`
    * Linuxの場合: `~/.omegat/plugins`

プラグインは、OmegaTのプラグインフォルダにコピーします。OSによって、導入するフォルダがことなります。

#### Linux

個人ユーザ導入の場合は、プラグインのjarファイルを ~/.omegat/plugins/ へ、全ユーザが利用できるようにするには、OmegaTの導入ディレクトリのプラグインフォルダヘ導入します。OmegaTは、インストーラをつかうと以下のフォルダや類似のフォルダにみつかるでしょう。

例 `/opt/omegat/OmegaT-4.3.0/plugins/` 

#### Windows

Windowsでは、プラグインをOmegaTが導入されたフォルダへいれることで利用できるようになります。例 `C:\Program Files\OmegaT` あるいは、ユーザの `Application Data`ディレクトリの たとえば `C:\Users\<username>\AppData\Roaming\OmegaT`です。

#### MacOS X

MacOS X では、プラグインを `/Users/<username>/Library/Preferences/OmegaT/plugins`へ導入することが推奨です。


## 2.2 EPWING辞書フォーマット対応プラグイン

EPWING形式の辞書に対応させるのが、[EPWING辞書フォーマット対応プラグイン](https://github.com/miurahr/omegat-plugin-epwing)です。

プラグインは、githubから入手できます。プラグインのリリースページをブラウザーでひらきます。

https://github.com/miurahr/omegat-plugin-epwing/releases

リリースされているバイナリのZipファイルをダウンロードします。

https://github.com/miurahr/omegat-plugin-epwing/releases/download/v2.0.1/omegat-plugin-epwing-2.0.1.zip

内容を解凍してください。解凍すると4つのファイルがはいっています。

* `README.md`
* `COPYING`
* `CHANGELOG.md`
* `omegat-plugin-epwing-2.0.1.jar`

このうち、最後のJARファイルがプラグインの本体です。


# 3. 辞書の利用

OmegaTでは、stardict 形式の辞書を導入すると、原文にあわせて自動的に辞書をひいてくれます。
stardict形式は、日本では知られていない為、辞書データを容易に入手することができません。
公開されているパブリックドメインの辞書データや、販売されている辞書データを変換して利用することになります。

日本では、電子辞書ファイルの日本独自の標準規格があります。EPWING形式です。JIS規格になっています。

## 3.1 ビジネス技術実用英語大辞典

海野さんが編纂された英和、和英辞典をつかいたいために、EPWING形式のサポートプラグインが開発されました。

* 『ビジネス技術実用英語大辞典Ｖ６　英和・和英』 プロジェクトポトス (2018年版)

EPWING形式は、OmegaT標準では対応していません。プラグインの導入が必要です。

## 3.2 英辞郎

英辞郎は、EDP(Electric Dictionary Project)が開発、頒布するプロプラエタリな辞書データです。収録されている単語数、用例数がおよそ200万と非常に多いのが特長です。2015年以降、最新データが含まれるDVD-ROM書籍などは、専用のアプリケーションと同梱されて暗号化された状態で販売されており、OmegaTから直接利用することはできません。

幸い利用可能な辞書データがダウンロード販売されており、2015年3月20日版のVersion 144.8ですが、それでも198万9500の項目がふくまれています。
販売サイト [Booth](https://booth.pm/ja/items/777563)

このテキストデータは、プログラムで変換処理をおこなうことで、OmegaTで利用可能になります。


## 3.3 EJDICT

EJDICTは、パブリックドメインの英和辞書データです。

https://kujirahand.com/web-tools/EJDictFreeDL.php



# 4 機械翻訳

近年、ニューラルネットワークによる機械学習のAI技術が飛躍的に向上したため、機械翻訳の品質が向上しています。
OmegaTのような翻訳メモリツールは、機械翻訳による自動処理ではなく、翻訳者の作業を支援するものですが、近年の機械翻訳の技術向上により、
翻訳メモリと機械翻訳をくみあわせて利用することが一般的になっています。

機械翻訳は、そのエンジンの技術も最先端であると同時に、エンジンへの学習によってその品質や性能がかわることから、
高度な知的財産とみなされています。利用にあたっては、サービス提供者との契約内容を十分に確認するようにしてください。

ここでは、Wikipediaやオープンソースなど、公益性の高い翻訳や、個人利用を行なう場合を想定して、無料で利用でき、
おすすめできる機械翻訳エンジンの利用方法を説明します。


## 4.1 みんなの自動翻訳 TexTra®

日本国政府の研究機関である、NICT 国立情報通信技術研究所が開発、運営する翻訳エンジンです。
https://textra.nict.go.jp/

本エンジンのAPIは、特筆すべきことに、OSSやWikipediaなど、公開ライセンスで公益性の高い公開文書への翻訳の利用は明示的に許諾されています。
また、様々な言語の組み合わせ(例：ロシア語ー英語、タイ語ー日本語など)が提供されているため、汎用的につかうことができます。

本エンジンを利用するには、インターネット接続が必要です。また、プラグインが必要です。

 みんなの自動翻訳 TexTra®プラグイン
 https://github.com/miurahr/omegat-textra-plugin

### 4.1.1 みんなの自動翻訳 TexTra®プラグインのインストール

プロジェクトの[リリースページ](https://github.com/miurahr/omegat-textra-plugin/releases)から
最新版のZIPファイルをダウンロードします。
たとえば、https://github.com/miurahr/omegat-textra-plugin/releases/download/v0.9.3/omegat-textra-plugin-0.9.3.zip

このZIPファイルを展開すると、5つほどのファイルが含まれています。
* README
* CHANGELOG
* DEVELOP
* COPYING
* omegat-textra-plugin-0.9.3.jar

この最後のJarファイルがプラグインの実体ファイルです。二章を参照して、プラグインのJARファイルを導入してください。

### みんなの自動翻訳 TexTra のID取得

ます、任意のWebブラウザをひらき、https://mt-auto-minhon-mlt.ucri.jgn-x.jp/ へ訪問します。

![](https://i.imgur.com/AaRIfL0.png)

このようなページが閲覧できます。
右上には、言語選択ダイアログがあり、英語のインターフェースも選択できます。

![](https://i.imgur.com/67tEsW4.png)

ここで、左上のログインボックスをさがしてください。

![](https://i.imgur.com/bt3j1R9.png)

新規登録ボタンをおして、登録を開始しましょう。

![](https://i.imgur.com/1tYtiQb.png)

ユーザID, パスワードなどを登録してください。

ここで、利用規約を確認するようにしてください。[利用規約](https://mt-auto-minhon-mlt.ucri.jgn-x.jp/content/policy/)はログインや登録しなくても確認できます。

#### TL;DR 規約の主なポイントは次のとおりです

* APIを利用するには、規約に同意する。
* 無償利用を非商用利用にたいして許諾する
* 法令又は公序良俗に反する行為など、禁止される用途がいろいろある
* ただし、OSSやWikipediaなどの公開文書等の翻訳には成果が無償公開される場合に利用可能

事業利用される場合は、NICTや開発会社にご相談ください。

登録がおわりましたら、ログインしてください。

### WEB API キーやシークレットの入手

OmegaTからAPI利用するためには、APIキーやシークレットの入手が必要です。

![](https://i.imgur.com/bUY9DBU.png)


メニューの一番したに、Web APIというメニューがあるので、クリックしてください。
そうしますと、様々なAPIが示されますが、その一番最初にでてくる、自動翻訳リクエストAPIを指定します。

![](https://i.imgur.com/uVCFQC2.png)

そうしますと、利用可能な言語のくみあわせ一覧が表示されます。

![](https://i.imgur.com/GtONOWd.png)

この一覧の右側に、APIという列があり、![](https://i.imgur.com/zjnCkVJ.png)
のマークをみつけることができます。


任意の (i) マークをクリックしてください。ポップアップウインドウがひらき、つぎのような画面が表示されます。ここで、API key やsecretは英数字の羅列ですが、セキュリティのため、画面では伏せ字にしています。

![](https://i.imgur.com/CXUg1ES.png)


このAPI Key, API SecretおよびログインIDをひかえてください。
設定に使用します。

### OmegaTの設定

ここで、OmegaTを起動してください。プラグインは導入すみですか？
設定メニューにある「機械翻訳(H)」を選択すると、サポートされている機械翻訳の一覧が表示されます。これから設定を行なって、Textra powered by NICTにチェックがはいるようにしていきましょう。

![](https://i.imgur.com/QIUQcwe.png)

OmegaTで「設定」→「環境設定」 を選択してください。
左側のメニューから機械翻訳を選択すると、このような画面が表示されます。

![](https://i.imgur.com/XGz4iVj.png)

ここで、中央の一覧をスクロールして、TexTraをみつけてワンクリックして選択してください。すると、右上にある「設定(Ｆ）」ボタンが有効化されさますので、クリックしてください。

![](https://i.imgur.com/pUoHe3i.png)

ここで、APIキーやAPIシークレットを入力してください。

また、翻訳モードは、言語によって選択可能なものがかわりますが、 英日翻訳であれば、「汎用NT」がおすすめです。

シークレットの入力をしましたらOKをおして保存してください。人によっては、マスターパスワードの設定がもとめられます。

次回からは、起動時にマスターパスワードがきかれるようになります。API secretなどの情報は暗号化されて保管されるようになりました。

![](https://i.imgur.com/6a7Osln.png)

最後に、翻訳エンジン一覧の右側のチェックボックスにチェックをいれて、有効化します。


以上で設定は完了です。

## 4.2 IBM Watson Language Translator

IBMのクラウドサービス Watson Language Translatorは商用の翻訳エンジンです。
さまざまな言語に対応しています。
![](https://i.imgur.com/P8LABkk.png)

Liteプランが用意されており、小規模な利用では、無償枠があります。

#### Lite

– Translate up to 1,000,000 Characters per Month

IBM Watsonの機械翻訳は、OmegaTで標準でサポートされています。
アカウントを作成し、アクセスURLとAPIキーを取得して、OmegaTのIBM Watsonの設定へ入力してください。



# 5. Wiki Translation

## 5.1 A Wiki contents

Launch OmegaT and create a new project. Let's call it ***Wiki project***.

Once you have decided on a subject on [Wikipedia](https://en.wikipedia.org/), you can use ***Mediawiki downloader feature*** of OmegaT, to download contents from Wikipedia page.
Start your OmegaT and open ***Wiki Project*** project.
Select menu ***File > Download from Mediawiki***, then you will find a dialog to ask ***Wikipedia URL***.
You now copy URL from above table or your browser's address field, then past it onto the dialog input box.

Your ***/source*** folder will now contain one or more Wiki file(s) end with ".UTF8" extension.


## 5.2 Translation of tags

- There special tags such as "<a0>...</a0>" and "<s0>" on HTML project in ***My Project-2***.
- There are wiki tags such as `===Title===`, `[https://some.URL/ | link name]` as-is with its source.

You need to keep Wiki tag with your own response. Otherwise, wiki rendering will be broken.
There is another caution for translation using translation memory.

- Wikipedia is subject to continual change. The pages listed here have been selected as suitable examples (and the “legacy” files have been created to correspond to them), but changes to them may make them less suitable, and they may even disappear or move elsewhere.

##  5.3 Use translated wiki text

When you are satisfied to translate it, you are ready to use translated contents. You now want to save your result. Select Menu ***File > Save***, then OmegaT save your translations into ***/omegat*** folder in the project automatically.
Next, you want to produce translated wiki text to use. Select Menu ***File > Generate translation***.

Please open ***Windows File Explorer*** from Windows menu, and go to ***Wiki Project*** folder ***/target***.
There will be files which extension is ***.UTF8*** files.

Let's check its content!

Open ***Notepad*** application from windwos menu, then ***Drag-and-Drop*** the file onto ***notepad***.
You will find a translated wiki contents on Notepad application.

If you want to contribute Wikipedia a bit or check your translation quality, let's go to your local language version of Wikipedia and search corresponding page! When click ***EDIT*** button of content on your web browser, you will see ***translated(or original for local) wiki source*** there.


## 5.4 Wiki contribution

A wiki download feature is not only for Wikipedia. There are so many wiki projects on the Internet which use Mediawiki engine. If you are volunteering to translate these wiki projects, the feature is for you.

Here is an incomplete list of known wiki projects that use Mediawiki.

- [WikiTravel | a free travel guide book](https://wikitravel.org/)
- [Gamepedia |a wiki collection of popular games](https://www.gamepedia.com/)
- [OpenStreetMap wiki](https://wiki.openstreetmap.org/)
- [Arch Linux documentation](https://wiki.archlinux.org/)
- etc.


# 6 クラウド翻訳サービス等との連携

近年、さまざまなプロジェクトでは、クラウド翻訳サービスで翻訳を推進、管理することがふえてきました。Webブラウザで翻訳作業をおこなうこともできるようになってきました。

There are several popular translation workflow/assistant services on the web. Here is a list of known services;

- Transifex
- Crowdin
- TranslateWiki
- Pootle
- Weblate

では、なぜデスクップアプリケーションで、翻訳をおこなうのでしょうか。
つぎのような観点があります。

1. 自分の翻訳データベースを利用して生産性を向上させる
2. 自分が保有する辞書や用例辞典を利用して、訳文の質を向上させる
3. ショートカットキーなどを多様して、生産性を向上させる
4. クラウドサービスにかかわらず、一貫性のあるUIを使用して、生産性を向上させる

ここでは、メジャーなクラウド翻訳サービスである、Transifex, Crowdinとの連携について解説します。

## 6.2 Transifex

A project on Transifex allows translators to download source and existing translations as files. Navigate to your translation project resources page, then click resource show context menu such as follows:

![Transifex example](https://raw.githubusercontent.com/miurahr/omegat-for-cat-beginners/master/images/en/transifex-download-po-file-menu.png)

A file format is a variation of the project settings, such as PO file, YAML, Qt translation(.ts), and so on. Thanks to OmegaT's support for various file format, you download the file into ***/source*** and  upload resulted translation from ***/target*** to website.


## 6.3 Crowdin

Crowdin support offline translation by utilize XLIFF standard format.

![crowdin download example](https://raw.githubusercontent.com/miurahr/omegat-for-cat-beginners/master/images/en/crowdin-download-xliff.png)

Caution: OmegaT 5.4.0 and later support collaboration with crowdin,
that require handling a XLIFF workflow feature.

As usual, you can download source XLIFF into ***/source*** directory, and after finishing translation, run ***File > generate target file*** then upload resulted XLIFF file in ***/target*** to Crowdin.


## 6.4. XLIFF

XLIFF (XML Localization Interchange File Format) is an XML-based bitext format for standardized localizable data exchange among CAT tools during localization process.

### 6.4.1 Basic Structure of XLIFF

There are XLIFF versions. v1.2 is a legacy format and still used widely. v2.x is international standardized version to recommended to use. 
 
XLIFF is XML-based and consist of several tags. Original contents are marked with source and localized contents are marked with target. There is an state attribute which indicate a translation status of marked sentence unit.

  
### 6.4.2 OmegaT filters

There are several options to utilize XLIFF format in OmegaT.

- Standard XLIFF filter
- Okapi plugin for OmegaT, XLIFF filter
- Okapi plugin for OmegaT, XLIFF2 filter

There are several pros and cons for each options.

#### A) Standard XLIFF filter

Standard XLIFF filter is a built-in filter on OmegaT.
It only support very basic XLIFF version 1.2 tags.
It has a notable feature to handle state attribute in OmegaT 5.4.0(beta) and later.


#### B) Okapi filters plugin for OmegaT, XLIFF filter

Okapi filters plugin which support XLIFF 1.2, and 2.0 and later. It provide two filters for XLIFF, XLIFF(okapi) and XLIFF2(okapi).
These filters recognize detailed and extensible tags. Note: state attribute is treated read-only in okapi filter, and  not able to change. 





# 7 アプリケーションのローカライズ

There are several known file format to localize desktop and web applications depends on what technology utilized.
Here is a table of notable application framework what file type is used.
A filter indicate with '(okapi)' is a filter provided by okapi filters plugin for OmegaT.

framework / langauge  |  file format         |  OmegaT filter
----------------------|----------------------|----------------
Swing / Java          |  properties          | Java resource bundle
JSP   / Java          |  properties          | Java resource bundle 
Qt / C++, Python      |  catalog (.ts)       | Qt TS files(okapi)
Android               |  resource file       | Android resources
Typo3 web framework   |  loc                 | typo3 LocManager
Django / Python       |  PO file (.po)       | PO 
Sphinx / Python       |  PO file (.po)       | PO
Angular / typescript  |  XLIFF               | XLIFF









## Appendix. 辞書ファイルや、文書ファイル形式の変換ツールやユーティリティ

### A.1 EPWING辞書の変換ツール. EBStudio

EBStudio2は、JIS X4081(EPWINGのサブセット)またはEBXA形式の電子辞書・電子書籍を作成するシェアウエアのアプリケーションです。

http://ebstudio.info/manual/EBStudio2/EBStudio2.html

辞書の入力テキストは、 HTML4.0、XHTML1.0、PDIC(PDIC形式/テキスト形式/1行テキスト形式)、 辞郎形式、plain-Text、CSVをサポートしています。

そのため、3.2 英辞郎 3.3 EJDICTのデータを、EPWINGに変換でき、OmegaTで利用できるようになります。

英辞郎の変換には、PDIC１行形式を入力形式 として選択してください。
EJDICTの変換には、TAB区切りのCSV形式がつかえそうです。


### A.2 stardict辞書変換ツール

OmegaTが既定でサポートしている辞書形式の stardict形式の辞書をあつかうツールキットに、stardict-toolsがあります。
主なディストリビューションでは、パッケージ配布が終了しているので、利用するには、最新版を個別にダウンロードして導入する必要があります。

http://stardict-4.sourceforge.net/

Windows、Linux用のバイナリが配布されています。


### A.3 各種変換ツール  Translate ツールキット

Translate ツールキットは、翻訳作業に便利なツール群が収録されたフリーソフトウエアのコレクションです。Pythonで記述されています。
POファイルやXLIFFファイルをとりあつかうことができます。ファイル形式の変換のほか、複数のPOファイルをマージする、品質チェックするなどの処理をおこなうことができます。

https://github.com/translate/translate

https://ja.wikipedia.org/wiki/Translate_Toolkit


主要なLinuxディストリビューションには、パッケージとして含まれています。
WindowsやMacOSでは、仮想マシン環境でLinuxを導入して作業することが推奨されています。

[インストール方法](http://docs.translatehouse.org/projects/translate-toolkit/en/stable/installation.html)

