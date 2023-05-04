# OmegaT - The CAT Power Tools


###### tags: `OmegaT`, `Translation`, `Tutorial`, `intermediate`, `Tips`


![Cover](https://i.imgur.com/xDqSCct.gif)
Serval wild cat (Felis Serval) in Africa, ClipArt ETC is copyright ©2020 by the University of South Florida [![Clipart ETC: Animals Menu](https://fcit.usf.edu/home/promo/ca/images/animals88x31.gif)](https://etc.usf.edu/clipart/sitemap/animals.htm)

## Copyright

Copyright (c) 2020 Hiroshi Miura

Permission is granted to copy, distribute and/or modify this document under the terms of the GNU Free Documentation License,
Version 1.3 or any later version published by the Free Software Foundation; with no Invariant Sections,
no Front-Cover Texts, and no Back-Cover Texts. A copy of the license is included in the section entitled "GNU Free Document License".

Cover illustration is from  the University of South Florida,
[ClipArt ETC](https://etc.usf.edu/clipart/) in grant of ClipArt ETC Free Classroom License.

Last update: September 2020  \
Refer to OmegaT version: 5.4.0

Screenshots from OmegaT version 5.4.0 on Windows 10 Enterprise(Build 19041)

Please note that owing to the pace at which OmegaT is being developed, the appearance of the screenshots and possibly some other information may have changed slightly.


## Preface

This tutorial is for intermediate OmegaT users who has already finished [the beginners guide](https://hackmd.io/@miurahr/ryTKGQKED/%2F%40miurahr%2FByx_z0smw) or equivalent, and provide advanced technics to utilize OmegaT efficiently and accelarate your translation work dramatically.

Topics in the tutorial are treated in standard manual, 
the tutorial describes topics in detail and hands-on.

The guide consists of the following chapters

- 1. Dictionaries
- 2. Wiki Translation
- 3. Work with other applications


# 1 Dictionaries

OmegaT has the capability to read electronic/machine readable bilingual/monolingual dictionaries
and show terms automatically from source sentence words.
You can use free dictionaries on the Internet, and/or your favorite
dictionary (when it is supported).

There is [a list of stardict dictionaries on the Internet](https://sites.google.com/site/gtonguedict/home/stardict-dictionaries). Some may be licensed as free data, some may be a proprietary data.


### 1.1 Free dictionary data

I'd like to advise you to use dictionary data licensed clearly for you. For your convenience, I put some link which is licensed as free for you

- [JMDict:Japnense-Multilingual dictionary](https://www.edrdg.org/jmdict/j_jmdict.html) ([Wikipedia article](https://en.wikipedia.org/wiki/EDICT))([license](https://www.edrdg.org/edrdg/licence.html))
- [CC-CEDICT: Chinese-English dictionary](https://cc-cedict.org/editor/editor.php) ([Wikipedia article](https://en.wikipedia.org/wiki/CEDICT))
- [startdict format](https://simonwiles.net/projects/) of several dictionaries
    - JMDict
    - CC-CEDICT
    - Buddhist Hybrid Sanskrit Dictionary
    - Kangxi Zidian 康熙字典
    - HanDeDict

You need to convert these dictionary data into ***startdict*** format to use with OmegaT. It requires some IT knowledge, so it is recommended for you to use pre-converted data.

If you know another good licensed dictionary data to use with OmegaT, please update the list. 



# 2. Wiki Translation

## 2.1 A Wiki contents

Launch OmegaT and create a new project. Let's call it ***Wiki project***.

Once you have decided on a subject on [Wikipedia](https://en.wikipedia.org/), you can use ***Mediawiki downloader feature*** of OmegaT, to download contents from Wikipedia page.
Start your OmegaT and open ***Wiki Project*** project.
Select menu ***File > Download from Mediawiki***, then you will find a dialog to ask ***Wikipedia URL***.
You now copy URL from above table or your browser's address field, then past it onto the dialog input box.

Your ***/source*** folder will now contain one or more Wiki file(s) end with ".UTF8" extension.


## 2.2 Translation of tags

- There special tags such as "<a0>...</a0>" and "<s0>" on HTML project in ***My Project-2***.
- There are wiki tags such as `===Title===`, `[https://some.URL/ | link name]` as-is with its source.

You need to keep Wiki tag with your own response. Otherwise, wiki rendering will be broken.
There is another caution for translation using translation memory.

- Wikipedia is subject to continual change. The pages listed here have been selected as suitable examples (and the “legacy” files have been created to correspond to them), but changes to them may make them less suitable, and they may even disappear or move elsewhere.


## 2.3 Use translated wiki text

When you are satisfied to translate it, you are ready to use translated contents. You now want to save your result. Select Menu ***File > Save***, then OmegaT save your translations into ***/omegat*** folder in the project automatically.
Next, you want to produce translated wiki text to use. Select Menu ***File > Generate translation***.

Please open ***Windows File Explorer*** from Windows menu, and go to ***Wiki Project*** folder ***/target***.
There will be files which extension is ***.UTF8*** files.

Let's check its content!

Open ***Notepad*** application from windwos menu, then ***Drag-and-Drop*** the file onto ***notepad***.
You will find a translated wiki contents on Notepad application.

If you want to contribute Wikipedia a bit or check your translation quality, let's go to your local language version of Wikipedia and search corresponding page! When click ***EDIT*** button of content on your web browser, you will see ***translated(or original for local) wiki source*** there.


## 2.4 Wiki contribution

A wiki download feature is not only for Wikipedia. There are so many wiki projects on the Internet which use Mediawiki engine. If you are volunteering to translate these wiki projects, the feature is for you.

Here is an incomplete list of known wiki projects that use Mediawiki.

- [WikiTravel | a free travel guide book](https://wikitravel.org/)
- [Gamepedia |a wiki collection of popular games](https://www.gamepedia.com/)
- [OpenStreetMap wiki](https://wiki.openstreetmap.org/)
- [Arch Linux documentation](https://wiki.archlinux.org/)
- etc.


# 3. work with other applications

## 3.1. Translation web platforms

There are several popular translation workflow/assistant services on the web. Here is a list of known services;

- Transifex
- Crowdin
- TranslateWiki
- Pootle
- Weblate

We pick two popular serices in the tutorial.


## 3.2 Transifex

A project on Transifex allows translators to download source and existing translations as files. Navigate to your translation project resources page, then click resource show context menu such as follows:

![Transifex example](https://raw.githubusercontent.com/miurahr/omegat-for-cat-beginners/master/images/en/transifex-download-po-file-menu.png)

A file format is a variation of the project settings, such as PO file, YAML, Qt translation(.ts), and so on. Thanks to OmegaT's support for various file format, you download the file into ***/source*** and  upload resulted translation from ***/target*** to website.


## 3.3 Crowdin

Crowdin support offline translation by utilize XLIFF standard format.

![crowdin download example](https://raw.githubusercontent.com/miurahr/omegat-for-cat-beginners/master/images/en/crowdin-download-xliff.png)

Caution: OmegaT 5.4.0 and later support collaboration with crowdin,
that require handling a XLIFF workflow feature.

As usual, you can download source XLIFF into ***/source*** directory, and after finishing translation, run ***File > generate target file*** then upload resulted XLIFF file in ***/target*** to Crowdin.


## 3.4. XLIFF

XLIFF (XML Localization Interchange File Format) is an XML-based bitext format for standardized localizable data exchange among CAT tools during localization process.

### 3.4.1 Basic Structure of XLIFF

There are XLIFF versions. v1.2 is a legacy format and still used widely. v2.x is international standardized version to recommended to use. 
 
XLIFF is XML-based and consist of several tags. Original contents are marked with source and localized contents are marked with target. There is an state attribute which indicate a translation status of marked sentence unit.

  
### 3.4.2 OmegaT filters

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





# Localization of Applications

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









