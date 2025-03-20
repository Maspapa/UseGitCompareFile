![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/userguide/celltype_numericupdowncell_decimalplaces.png)
数値型セル（NumericUpDownCell）の値に小数点以下の桁数を表示する方法はSystem.Windows.Forms.NumericUpDownコントロールと同じです。[NumericUpDownCell.DecimalPlaces](gcdocsite__documentlink?toc-item-id=089d36d5-dabc-4bd8-bfaf-5f7f77796a3b)プロパティに表示する小数点以下の桁数を設定します。

## デザイナによる設定

1. 行（Row）に数値型セルを追加する。（例：numericUpDownCell1）
2. numericUpDownCell1を選択し、プロパティウィンドウでnumericUpDownCell1.DecimalPlacesプロパティを3に設定する。

## コーディングによる設定

```csharp
using GrapeCity.Win.MultiRow;

NumericUpDownCell numericUpDownCell1 = new NumericUpDownCell();
numericUpDownCell1.Name = "numericUpDownCell1";
numericUpDownCell1.DecimalPlaces = 3;
numericUpDownCell1.Value = 10.23;

gcMultiRow1.Template = Template.CreateGridTemplate(new Cell[] { numericUpDownCell1 });
gcMultiRow1.RowCount = 10;
```

```vbnet
Imports GrapeCity.Win.MultiRow

Dim NumericUpDownCell1 As New NumericUpDownCell()
NumericUpDownCell1.Name = "NumericUpDownCell1"
NumericUpDownCell1.DecimalPlaces = 3
NumericUpDownCell1.Value = 10.23

GcMultiRow1.Template = Template.CreateGridTemplate(New Cell() {NumericUpDownCell1})
GcMultiRow1.RowCount = 10
```

## 関連トピック

[数値型セル（NumericUpDownCell）](gcdocsite__documentlink?toc-item-id=7bc40421-e50f-4b59-9ec2-af44aadbf42f)
[スピンボタンの非表示](gcdocsite__documentlink?toc-item-id=b3b972ce-35ec-4560-9dea-35f794db8ae8)
[数値の桁区切り表示](gcdocsite__documentlink?toc-item-id=a3d312ee-c86f-4b9d-900e-b92dcac0ead5)
[マイナスの値の赤字表示](gcdocsite__documentlink?toc-item-id=1527ec60-cbf7-44cc-939b-586e69b4880b)