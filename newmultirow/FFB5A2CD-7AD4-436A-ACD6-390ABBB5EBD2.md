MultiRowは、印刷データの背面に透かしを入れて印刷できます。

## 透かしの設定

透かしを設定するには、[PrintSettings.Watermark](gcdocsite__documentlink?toc-item-id=8f6b9bc8-0295-4a32-bfac-a19e9b2a928f)プロパティに画像型のデータを設定します。
```csharp
gcMultiRow1.PrintSettings.Watermark = new Bitmap(@"test.bmp");
```

```vbnet
GcMultiRow1.PrintSettings.Watermark = New Bitmap("test.bmp")
```

## 透かしの配置

透かしの配置場所を設定するには、[PrintSettings.WatermarkAlignment](gcdocsite__documentlink?toc-item-id=70dc55b5-93dd-454c-ae9a-7e8efcc4ddb8)プロパティを使用します。
```csharp
gcMultiRow1.PrintSettings.WatermarkAlignment = ContentAlignment.BottomRight;
```

```vbnet
GcMultiRow1.PrintSettings.WatermarkAlignment = ContentAlignment.BottomRight
```

## 透かしのサイズ

透かしのサイズを設定するには、[PrintSettings.WatermarkSizeMode](gcdocsite__documentlink?toc-item-id=aad0a0c8-3793-42bb-8ba2-22e86235e3fb)プロパティを使用します。
```csharp
gcMultiRow1.PrintSettings.WatermarkSizeMode = GrapeCity.Win.MultiRow.SizeMode.Stretch;
```

```vbnet
GcMultiRow1.PrintSettings.WatermarkSizeMode = GrapeCity.Win.MultiRow.SizeMode.Stretch
```

## 透かしの印刷ページ指定

透かしを印刷するページを設定するには、[PrintSettings.WatermarkPrintOnPages](gcdocsite__documentlink?toc-item-id=eef0d943-9c6b-4fc7-af14-386fa9f19710)プロパティを使用します。
```csharp
gcMultiRow1.PrintSettings.WatermarkPrintOnPages = "3-5";
```

```vbnet
GcMultiRow1.PrintSettings.WatermarkPrintOnPages = "3-5"
```

## 透かしの不透明度

透かしの不透明度を設定するには、[PrintSettings.WatermarkOpacity](gcdocsite__documentlink?toc-item-id=913b2093-bfd4-4acb-b36e-b6c07b6150cb)プロパティを使用します。
```csharp
gcMultiRow1.PrintSettings.WatermarkOpacity = 0.5;
```

```vbnet
GcMultiRow1.PrintSettings.WatermarkOpacity = 0.5
```

## 透かしの前面表示

既定では、グリッドに重なっている透かしは印刷されませんが、[Section.PrintBackground](gcdocsite__documentlink?toc-item-id=993764cf-1458-4d11-8664-12c9fa3f8828)プロパティにFalseを設定すると、透かしを前面に表示して印刷できます。
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/userguide/printing_watermark_01.png)
```csharp
using GrapeCity.Win.MultiRow;

TextBoxCell textBoxCell1 = new TextBoxCell();
textBoxCell1.Name = "textBoxCell1";
TextBoxCell textBoxCell2 = new TextBoxCell();
textBoxCell2.Name = "textBoxCell2";

Template template =  Template.CreateGridTemplate(new Cell[] {textBoxCell1, textBoxCell2});
template.Row.PrintBackground = false;

gcMultiRow1.Template = template;
gcMultiRow1.RowCount = 10;
```

```vbnet
Imports GrapeCity.Win.MultiRow

Dim TextBoxCell1 As New TextBoxCell()
TextBoxCell1.Name = "TextBoxCell1"
Dim TextBoxCell2 As New TextBoxCell()
TextBoxCell2.Name = "TextBoxCell2"

Dim Template1 As Template = Template.CreateGridTemplate(New Cell() {TextBoxCell1, TextBoxCell2})
Template1.Row.PrintBackground = False

GcMultiRow1.Template = Template1
GcMultiRow1.RowCount = 10
```

## 関連トピック

[印刷と印刷プレビュー](gcdocsite__documentlink?toc-item-id=5b3a3722-2e41-4abb-b461-77030eab0b12)
[簡易な印刷](gcdocsite__documentlink?toc-item-id=3951a446-7fd8-464c-9e71-a36f3e83307f)
[印刷のカスタマイズ](gcdocsite__documentlink?toc-item-id=f929245c-c3d2-42d3-b12f-a4df3fe50c44)
[印刷スタイル](gcdocsite__documentlink?toc-item-id=aa24eab5-0dba-4555-aab5-5cb3bb11a11e)
[ページング モード](gcdocsite__documentlink?toc-item-id=8d04ca3a-1cf5-42a2-a3f7-faa8d97cda95)
[印刷範囲の指定](gcdocsite__documentlink?toc-item-id=578fac0a-450b-484d-809b-3d44fcfc82c6)
[改ページ位置の指定](gcdocsite__documentlink?toc-item-id=c78279bb-782e-4308-ba68-528c1a91efdf)
[空白行の印刷指定](gcdocsite__documentlink?toc-item-id=34938ed2-ecdf-48a4-a270-f790bcf91fc4)
[列ヘッダセクションごとの印刷設定](gcdocsite__documentlink?toc-item-id=9861ae8a-85df-4af0-9bb2-c896038b70af)