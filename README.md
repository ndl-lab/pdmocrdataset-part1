# PDMOCRデータセットパート１

## 概要

国立国会図書館（以下、「当館」といいます。）が令和3年度にLINE株式会社に委託して実施したデジタル化資料のOCRテキスト化事業の一環として、
テキスト化性能の改善を目的として国立国会図書館の保有するデジタル化資料から作成した機械学習用データセットのうち、
著作権保護期間の満了した資料から作成されたサブセットを公開するリポジトリです。


このデータセットを利用して性能改善を行ったOCRを利用して作成したテキストデータは、
次世代デジタルライブラリー(https://lab.ndl.go.jp/dl/
)の全文検索機能・本文ダウンロード機能として提供を開始しているほか、令和5年1月にリニューアル予定の国立国会図書館デジタルコレクションの全文検索機能として提供予定です。


## データセットのURL

次に挙げる2つの形式で公開しています。
なお、いずれの形式においても、文字コードの包摂は行っていません。
旧字体や異体字についても、視認された通りの表記で基本的に入力されています。

### 1. LINE形式(URLを入れる)

LINE株式会社が作成したアノテーションデータ(JSONフォーマット)及びアノテーションデータに対応する画像データからなります。


### 2. PascalVOC 1.1形式(https://lab.ndl.go.jp/dataset/pdm_ocr_dataset/line/tosho_all_pascalvoc1.1.zip)

当館で納入物の検品を実施した際にLINE形式をもとに変換したPascalVOC形式のアノテーションデータ（xmlフォーマット）及びアノテーションデータに対応する画像データからなります。
ファイルサイズを小さく抑えるため、LINE形式の画像データの縦横比を半分にしています。（アノテーションデータに含まれる座標情報も同様）
内部のテキスト情報はオブジェクト毎にattributeとして記述しています。


## 作成対象とした画像のメタデータ





## アノテーション例


### 1. LINE形式(URLを入れる)


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
    <name>text</name>　（内部にテキストを読むobjectはtext、内部を読まないobjectはdontcareとなる。）
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


