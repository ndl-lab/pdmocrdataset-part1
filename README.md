# パブリックドメインOCR学習用データセット（令和3年度OCRテキスト化事業分）

国立国会図書館（以下、「当館」といいます。）が令和3年度にLINE株式会社に委託して実施したデジタル化資料のOCRテキスト化事業の成果物を公開しています。
具体的には、テキスト化性能の改善を目的として当館の保有するデジタル化資料から作成したOCR学習用途の機械学習データセットのうち、
著作権保護期間の満了した資料から作成されたデータセットを公開するリポジトリです。
2022年4月末現在、2,713画像分を公開しています。

## 概要

このデータセットを利用して性能改善を行ったOCRを利用して作成したテキストデータは、
次世代デジタルライブラリー(https://lab.ndl.go.jp/dl/
)の全文検索機能・本文ダウンロード機能として提供を開始しているほか、令和4年12月にリニューアル予定の国立国会図書館デジタルコレクションの全文検索機能として提供予定です。


## データセットのURL

次に挙げる2種類の形式で公開しています。

なお、いずれの形式においても文字コードの包摂は行っていません。旧字体や異体字についても、視認された通りの表記で入力されています。

### 1. JSON形式(https://lab.ndl.go.jp/dataset/pdm_ocr_dataset/line/tosho_all_linejson.zip) (※ファイルサイズ:4.8 GB)

JSONフォーマットで作成したアノテーションデータ及びアノテーションデータに対応する画像データからなります。


### 2. PascalVOC 1.1形式(https://lab.ndl.go.jp/dataset/pdm_ocr_dataset/line/tosho_all_pascalvoc1.1.zip) (※ファイルサイズ:1.8 GB)

当館で納入物の検品を実施した際にJSON形式をもとに変換したPascalVOC形式のアノテーションデータ（xmlフォーマット）及びアノテーションデータに対応する画像データからなります。
ファイルサイズを小さく抑えるため、JSON形式の画像データのサイズ（縦幅及び横幅）を半分にしています。（アノテーションデータに含まれる座標情報も同様）
内部のテキスト情報はオブジェクト毎にattributeとして記述しています。
出力にはcvat(https://github.com/openvinotoolkit/cvat
)のエクスポート機能を利用しています。

## データセットの権利
「PDM（パブリック・ドメイン・マーク）」&lt; https://creativecommons.org/publicdomain/mark/1.0/deed.ja &gt;

※著作権保護期間満了資料のみを利用しています。

このデータセットは、自由な二次利用が可能です。ただし、二次利用に際しては、次の事項へのご配慮をお願いいたします。これらのお願いは法的な契約ではありませんが、できる限りご留意の上でご利用くださるよう、ご協力をお願いします。

- データを編集・加工等して利用する場合は、それを行ったことを記載してください。編集・加工等を、元となる作品・原資料の作者や当館が行なったかのような態様で公表しないようご留意ください。
- 当該データが自由に二次利用可能であることの表記を保持してください。
- 元となる作品や、その作者の名声を傷つける形での利用は行わないようご留意ください。また、元となる作品に関わる文化やコミュニティへの配慮を行ってください。
- 著作権以外の権利（著作者人格権、著作隣接権、肖像権、パブリシティ権、プライバシー権、商標権等）にも留意し、関連法令を遵守してください。


## ディレクトリ構成
データセット作成対象とした図書資料の刊行年代（10年刻み）及び分類（日本十進分類法における4類・5類・6類の資料を理系、それ以外を文系と定義）によりディレクトリを分けています。

### 1. JSON形式

```
tosho_all_linejson
├── img
│?? ├── tosho_1870_bunkei
│?? ├── tosho_1870_rikei
│?? ├── tosho_1880_bunkei
│?? ├── tosho_1880_rikei
│?? ├── tosho_1890_bunkei
│?? ├── tosho_1890_rikei
│?? ├── tosho_1900_bunkei
│?? ├── tosho_1900_rikei
│?? ├── tosho_1910_bunkei
│?? ├── tosho_1910_rikei
│?? ├── tosho_1920_bunkei
│?? ├── tosho_1920_rikei
│?? ├── tosho_1930_bunkei
│?? ├── tosho_1930_rikei
│?? ├── tosho_1940_bunkei
│?? └── tosho_1940_rikei
└── json
    ├── tosho_1870_bunkei
    ├── tosho_1870_rikei
    ├── tosho_1880_bunkei
    ├── tosho_1880_rikei
    ├── tosho_1890_bunkei
    ├── tosho_1890_rikei
    ├── tosho_1900_bunkei
    ├── tosho_1900_rikei
    ├── tosho_1910_bunkei
    ├── tosho_1910_rikei
    ├── tosho_1920_bunkei
    ├── tosho_1920_rikei
    ├── tosho_1930_bunkei
    ├── tosho_1930_rikei
    ├── tosho_1940_bunkei
    └── tosho_1940_rikei
```

### 2. PascalVOC 1.1形式

```
tosho_all_pascalvoc1.1
├── tosho_1870_bunkei
│?? ├── Annotations
│?? │?? └── pdmlinetrainimg
│?? │??     └── tosho_1870_bunkei
│?? ├── ImageSets
│?? │?? ├── Action
│?? │?? ├── Layout
│?? │?? ├── Main
│?? │?? └── Segmentation
│?? └── JPEGImages
│??     └── pdmlinetrainimg
│??         └── tosho_1870_bunkei
├── tosho_1870_rikei
│?? ├── Annotations
│?? │?? └── pdmlinetrainimg
│?? │??     └── tosho_1870_rikei
│?? ├── ImageSets
│?? │?? ├── Action
│?? │?? ├── Layout
│?? │?? ├── Main
│?? │?? └── Segmentation
│?? └── JPEGImages
│??     └── pdmlinetrainimg
│??         └── tosho_1870_rikei
（以下略）
```

## 作成対象とした画像のメタデータ

以下を参照してください。

[metadata](./info.csv)



## アノテーション例


### 1. JSON形式

```
{
  "boxes": [
    {
      "box_id": 1,
      "text": "五百三十八",
      "orientation": "vertical",
      "quad": {
        "x1": 2945,
        "y1": 1856,
        "x2": 2988,
        "y2": 1856,
        "x3": 2988,
        "y3": 2075,
        "x4": 2945,
        "y4": 2075
      }
    },
    {
      "box_id": 2,
      "text": "ノ未來ノ行事如何或ハ我輩猶豫ノ際ニ於キテノ善處法ハ如何或ハ古",
      "orientation": "vertical",（※縦書きの場合vertical、横書きの場合horizontalが入る）
      "quad": {(※領域を囲む頂点の座標が入る)
        "x1": 2843,
        "y1": 576,
        "x2": 2893,
        "y2": 577,
        "x3": 2877,
        "y3": 2217,
        "x4": 2827,
        "y4": 2216
      }
    },
    (中略)
    "dontcare": [　(※中身を読まなくてよい領域の座標が配列として入る)
    [
      {
        "x1": 965,
        "y1": 446,
        "x2": 1218,
        "y2": 446,
        "x3": 1218,
        "y3": 723,
        "x4": 965,
        "y4": 723
      }
    ]
  ]
}

```

### 2. PascalVOC 1.1形式

```
<annotation>
  <folder>pdmlinetrainimg/tosho</folder>
  <filename>pdmlinetrainimg/tosho_1870_bunkei/753057_R0000281.jpg</filename>
  <source>
    <database>Unknown</database>
    <annotation>Unknown</annotation>
    <image>Unknown</image>
  </source>
  <size>
    <width>1612</width> （※画像幅）
    <height>1280</height>　（※画像高さ）
    <depth></depth>
  </size>
  <segmented>0</segmented>
  <object>
    <name>text</name>　（※attributeにテキストを含むobjectはtext、テキストを含まない、中身を読まなくてよいobjectはdontcareが入る）
    <occluded>0</occluded>
    <bndbox>
      <xmin>1413.0</xmin>
      <ymin>288.0</ymin>
      <xmax>1446.0</xmax>
      <ymax>1108.0</ymax>
    </bndbox>
    <attributes>
      <attribute>
        <name>contents</name>
        <value>ノ未來ノ行事如何或ハ我輩猶豫ノ際ニ於キテノ善處法ハ如何或ハ古</value>
      </attribute>
    </attributes>
  </object>
  （以下略）
```


