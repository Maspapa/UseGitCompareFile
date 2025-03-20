PlusPakCell の名前空間 GrapeCity.Win.MultiRow.PlusPak と PlusPak の名前空間を共に省略すると、ビルド時に「あいまいな参照」エラーが発生することがあります。これは、PlusPakCell がパフォーマンスを最適化するために PlusPak と同名のクラスのサブセットを提供していることが原因です。
例：

```csharp
using GrapeCity.Win.MultiRow.PlusPak;
using GrapeCity.Win.Calendar;

Weekdays a; // あいまいな参照エラー
```

```vbnet
Imports GrapeCity.Win.MultiRow.PlusPak
Imports GrapeCity.Win.Calendar

Dim a As Weekdays ' あいまいな参照エラー
```

「あいまいな参照」エラーを避けるために、次のようなコーディング方法をおすすめします。

```csharp
using PlusPakCell = GrapeCity.Win.MultiRow.PlusPak;
using GrapeCity.Win.Calendar;

PlusPakCell.Weekdays a; // PlusPakCell の参照
Weekdays b; // PlusPak の参照
```

```vbnet
Imports PlusPakCell = GrapeCity.Win.MultiRow.PlusPak
Imports GrapeCity.Win.Calendar

Dim a As PlusPakCell.Weekdays ' PlusPakCell の参照
Dim b As Weekdays ' PlusPak の参照
```

## 関連トピック

[PlusPakCellの使い方](gcdocsite__documentlink?toc-item-id=f3782c2d-37c3-407d-9aaf-2a64d3af122f)