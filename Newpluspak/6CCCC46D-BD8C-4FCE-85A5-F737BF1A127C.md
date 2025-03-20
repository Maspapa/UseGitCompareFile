あらかじめ定義されたスタイルのほかに、塗りつぶしの色、グラデーションそして画像を指定することで進行状況の描画をカスタマイズすることが可能です。なお、コントロールをカスタマイズするには、[FlatStyle](gcdocsite__documentlink?toc-item-id=6d2e3f79-0fa2-4313-9c96-9769659f1a3e) プロパティを **System 以外**の値に設定する必要があります。

## カスタマイズに使用するプロパティ

カスタマイズに使用するプロパティは、主に次のとおりです。

| プロパティ | 説明 |
| ----- | --- |
| BackColor | コントロールの背景色 |
| BackGradientEffect | 背景部分を塗りつぶすために使用されるグラデーション |
| BackgroundImage | コントロールの背景イメージ |
| BackgroundImageLayout | 背景イメージのレイアウト |
| BorderStyle | 境界線のスタイル |
| FillColor | 完了部分を塗りつぶす色 |
| FillForeColor | 完了部分の前景色 |
| FillGradientEffect | 完了部分を塗りつぶすために使用されるグラデーション |
| FillImage | 完了部分を塗りつぶすために使用されるイメージ |
| FillImageLayout | 完了部分のイメージのレイアウト |
| SingleBorderColor | コントロールの境界線の色 |

## グラデーション効果の使用

グラデーション効果を使用した背景と完了部分を持つ GcProgressBar コントロールは、次のサンプルコードのように設定します。

```csharp
// gcProgressBar1のフラットスタイルを設定します。
gcProgressBar1.FlatStyle = System.Windows.Forms.FlatStyle.Standard;

// gcProgressBar1のスタイルを連続した塗りつぶしに設定します。
gcProgressBar1.Style = GrapeCity.Win.Bars.ProgressStyle.Continuous;

// コントロールの境界線およびその色を定義します。
gcProgressBar1.BorderStyle = BorderStyle.FixedSingle;
gcProgressBar1.SingleBorderColor = System.Drawing.Color.Navy;

// コントロールの背景グラデーションを設定します。
GrapeCity.Win.Common.GradientEffect myBackGradientEffect1 = new GrapeCity.Win.Common.GradientEffect();
myBackGradientEffect1.Style = GrapeCity.Win.Common.GradientStyle.Vertical;
myBackGradientEffect1.Direction = GrapeCity.Win.Common.GradientDirection.Forward;
myBackGradientEffect1.StartColor = Color.White;
myBackGradientEffect1.EndColor = Color.Gray;

// 背景グラデーションをgcProgressBar1に設定します。
gcProgressBar1.BackGradientEffect = myBackGradientEffect1;

// 完了部分の前景色を設定します。
gcProgressBar1.FillForeColor = System.Drawing.Color.WhiteSmoke;

// コントロールの完了部分グラデーションを設定します。
GrapeCity.Win.Common.GradientEffect myFillGradientEffect1 = new GrapeCity.Win.Common.GradientEffect();
myFillGradientEffect1.Style = GrapeCity.Win.Common.GradientStyle.Vertical;
myFillGradientEffect1.Direction = GrapeCity.Win.Common.GradientDirection.Forward;
myFillGradientEffect1.StartColor = Color.Wheat;
myFillGradientEffect1.EndColor = Color.Orange;

// 完了部分グラデーションをgcProgressBar1に設定します。
gcProgressBar1.FillGradientEffect = myFillGradientEffect1;
```

```vbnet
' GcProgressBar1のフラットスタイルを設定します。
GcProgressBar1.FlatStyle = System.Windows.Forms.FlatStyle.Standard

' GcProgressBar1のスタイルを連続した塗りつぶしに設定します。
GcProgressBar1.Style = GrapeCity.Win.Bars.ProgressStyle.Continuous

' コントロールの境界線およびその色を定義します。
GcProgressBar1.BorderStyle = BorderStyle.FixedSingle
GcProgressBar1.SingleBorderColor = System.Drawing.Color.Navy

' コントロールの背景グラデーションを設定します。
Dim myBackGradientEffect1 As New GrapeCity.Win.Common.GradientEffect
myBackGradientEffect1.Style = GrapeCity.Win.Common.GradientStyle.Vertical
myBackGradientEffect1.Direction = GrapeCity.Win.Common.GradientDirection.Forward
myBackGradientEffect1.StartColor = Color.White
myBackGradientEffect1.EndColor = Color.Gray

' 背景グラデーションをGcProgressBar1に設定します。
GcProgressBar1.BackGradientEffect = myBackGradientEffect1

' 完了部分の前景色を設定します。
GcProgressBar1.FillForeColor = System.Drawing.Color.WhiteSmoke

' コントロールの完了部分グラデーションを設定します。
Dim myFillGradientEffect1 As New GrapeCity.Win.Common.GradientEffect
myFillGradientEffect1.Style = GrapeCity.Win.Common.GradientStyle.Vertical
myFillGradientEffect1.Direction = GrapeCity.Win.Common.GradientDirection.Forward
myFillGradientEffect1.StartColor = Color.Wheat
myFillGradientEffect1.EndColor = Color.Orange

' 完了部分グラデーションをGcProgressBar1に設定します。
GcProgressBar1.FillGradientEffect = myFillGradientEffect1
```

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gcprogressbar.customizesample1.png)

## イメージの使用

次のサンプルコードは、イメージを用いて完了部分を塗りつぶす GcProgressBar コントロールの作成方法を示します。

```csharp
// GcProgressBar1のフラットスタイルを設定します。
gcProgressBar1.FlatStyle = System.Windows.Forms.FlatStyle.Flat;

// コントロールの境界線スタイルを設定します。
gcProgressBar1.BorderStyle = BorderStyle.Fixed3D;

// GcProgressBar1のスタイルを連続した塗りつぶしに設定します。
gcProgressBar1.Style = GrapeCity.Win.Bars.ProgressStyle.Continuous;

// コントロールの背景グラデーションを設定します。
GrapeCity.Win.Common.GradientEffect myBackGradientEffect1 = new GrapeCity.Win.Common.GradientEffect();
myBackGradientEffect1.Style = GrapeCity.Win.Common.GradientStyle.Horizontal;
myBackGradientEffect1.Direction = GrapeCity.Win.Common.GradientDirection.Center;
myBackGradientEffect1.StartColor = Color.White;
myBackGradientEffect1.EndColor = Color.Pink;

// 背景グラデーションをGcProgressBar1に設定します。
gcProgressBar1.BackGradientEffect = myBackGradientEffect1;

// テキストの色を設定します。
gcProgressBar1.ForeColor = Color.Blue;

// 完了部分を塗りつぶすためのイメージを設定します。
Image myFillImage = Image.FromFile("Arrow.bmp");
gcProgressBar1.FillImage = myFillImage;
gcProgressBar1.FillImageLayout = ImageLayout.Stretch;

// 完了部分の塗りつぶし色を透過に設定します。
gcProgressBar1.FillColor = Color.Transparent;
```

```vbnet
' GcProgressBar1のフラットスタイルを設定します。
GcProgressBar1.FlatStyle = System.Windows.Forms.FlatStyle.Flat

' コントロールの境界線スタイルを設定します。
GcProgressBar1.BorderStyle = BorderStyle.Fixed3D

' GcProgressBar1のスタイルを連続した塗りつぶしに設定します。
GcProgressBar1.Style = GrapeCity.Win.Bars.ProgressStyle.Continuous

' コントロールの背景グラデーションを設定します。
Dim myBackGradientEffect1 As New GrapeCity.Win.Common.GradientEffect
myBackGradientEffect1.Style = GrapeCity.Win.Common.GradientStyle.Horizontal
myBackGradientEffect1.Direction = GrapeCity.Win.Common.GradientDirection.Center
myBackGradientEffect1.StartColor = Color.White
myBackGradientEffect1.EndColor = Color.Pink

' 背景グラデーションをGcProgressBar1に設定します。
GcProgressBar1.BackGradientEffect = myBackGradientEffect1

' テキストの色を設定します。
GcProgressBar1.ForeColor = Color.Blue

' 完了部分を塗りつぶすためのイメージを設定します。
Dim myFillImage As Image = Image.FromFile("Arrow.bmp")
GcProgressBar1.FillImage = myFillImage
GcProgressBar1.FillImageLayout = ImageLayout.Stretch

' 完了部分の塗りつぶし色を透過に設定します。
GcProgressBar1.FillColor = Color.Transparent
```

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gcprogressbar.customizesample2.png)

## 関連トピック

[GcProgressBarコントロール](gcdocsite__documentlink?toc-item-id=d33d3278-ef9c-4ab3-906a-e06a035034f7)
[進行状況の設定](gcdocsite__documentlink?toc-item-id=d62a2f0c-bdf1-42c3-84f7-ebee10050cf1)
[バーの外観変更](gcdocsite__documentlink?toc-item-id=ef661071-c4ef-473f-81f5-085a30474652)
[テキストの設定](gcdocsite__documentlink?toc-item-id=27a0a00c-5dfe-4596-a7c7-5d58a5710c73)