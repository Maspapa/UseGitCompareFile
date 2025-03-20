## <span class="SectionHeadingText">文字の立体表示</span>

[TextEffect](gcdocsite__documentlink?toc-item-id=eb3d3f33-dc4f-4ac0-92c8-4dacfe303d30)プロパティで、文字を立体的に表示できます。立体表示には **Inset**（強いくぼみ）、**InsetLite**（軽いくぼみ）、**Raised**（強い浮き出し）、**RaisedLite**（軽い浮き出し）があります。

```csharp
// 文字を強い浮き出しの立体表示にします。
gcLabel1.TextEffect = GrapeCity.Win.Common.TextEffect.Raised;
```

```vbnet
' 文字を強い浮き出しの立体表示にします。
GcLabel1.TextEffect = GrapeCity.Win.Common.TextEffect.Raiseds
```

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gclabel.texteffect.png)

## パターン効果とグラデーション

GcLable コントロールは、立体表示機能に加えて [GradientEffect](gcdocsite__documentlink?toc-item-id=941b4faf-7c73-458e-8d17-af33e42623f3)プロパティによる背景のグラデーションと、PatternEffect プロパティによる模様も設定できます。

```csharp
using GrapeCity.Win.Common;

// グラデーションを作成します
GradientEffect objGradientEffect = new GradientEffect(GradientStyle.Vertical, GradientDirection.Forward, Color.SkyBlue, Color.Blue);
// グラデーションを適用します
gcLabel1.GradientEffect = objGradientEffect;

// パターン効果を作成します
PatternEffect objPatternEffect = new PatternEffect(PatternStyle.DiagonalCross, Color.Red);
// パターン効果を適用します
gcLabel2.PatternEffect = objPatternEffect;
```

```vbnet
Imports GrapeCity.Win.Common

' グラデーションを作成します
Dim objGradientEffect As New GradientEffect(GradientStyle.Vertical, GradientDirection.Forward, Color.SkyBlue, Color.Blue)
' グラデーションを適用します
GcLabel1.GradientEffect = objGradientEffect

' パターン効果を作成します
Dim objPatternEffect As New PatternEffect(PatternStyle.DiagonalCross, Color.Red)
' パターン効果を適用します
GcLabel2.PatternEffect = objPatternEffect
```

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gclabel.effect.png)

## アーチ文字

[TextArcMode](gcdocsite__documentlink?toc-item-id=eb8b3729-8734-4df9-bd09-0cd93fcbf262)プロパティで、アーチ型に表示できます。アーチ型には **ArchUp**（上向き）、 **ArchDown**（下向き）、**Circle**（円）があります。

```csharp
gcLabel1.TextArcMode = GrapeCity.Win.Buttons.TextArcMode.ArchUp;
```

```vbnet
GcLabel1.TextArcMode = GrapeCity.Win.Buttons.TextArcMode.ArchUp
```

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gclabel.arch.png)

## 画像の表示

GcLabel コントロールは Image プロパティで画像を表示できます。画像の配置は ImageAlign プロパティを使用します。
また、TextArcMode プロパティと組み合わせて使用することもできます。

```csharp
gcLabel1.Image = new Bitmap(@"c:\icon.png");
gcLabel1.ImageAlign = GrapeCity.Win.Common.ImageAlign.Bottom;

gcLabel1.TextArcMode = GrapeCity.Win.Buttons.TextArcMode.ArchUp;
```

```vbnet
GcLabel1.Image = New Bitmap("c:\icon.png")
GcLabel1.ImageAlign = GrapeCity.Win.Common.ImageAlign.Bottom

GcLabel1.TextArcMode = GrapeCity.Win.Buttons.TextArcMode.ArchUp
```

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gclabel.image.png)

## テキストの中抜き効果

[OutlineEffect](gcdocsite__documentlink?toc-item-id=c2b79eed-cc48-4c4d-87f7-9d887f506737)クラスを使用すると、テキストの中抜き効果を表示できます。中抜きの効果では、テキストの塗りつぶし色および境界線の色と種類を設定できます。

```csharp
GrapeCity.Win.Buttons.OutlineEffect outlineEffect1 = new GrapeCity.Win.Buttons.OutlineEffect();
outlineEffect1.FillColor = Color.Yellow;
outlineEffect1.LineColor = Color.Red;
outlineEffect1.LineStyle = GrapeCity.Win.Buttons.OutlineStyle.Single;

gcLabel1.OutlineEffect = outlineEffect1;
```

```vbnet
Dim outlineEffect1 As New GrapeCity.Win.Buttons.OutlineEffect()
outlineEffect1.FillColor = Color.Yellow
outlineEffect1.LineColor = Color.Red
outlineEffect1.LineStyle = GrapeCity.Win.Buttons.OutlineStyle.Single

GcLabel1.OutlineEffect = outlineEffect1
```

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gclabel.outline.png)

## テキストの影付き効果

[ShadowEffect](gcdocsite__documentlink?toc-item-id=dcf8edcc-889d-49d7-9543-8b930eb78f8e)クラスを使用すると、テキストの影付き効果を表示できます。影付き効果では、影の色と深さを設定できます。

```csharp
GrapeCity.Win.Buttons.ShadowEffect shadowEffect1 = new GrapeCity.Win.Buttons.ShadowEffect();
shadowEffect1.Color = Color.Silver;
shadowEffect1.Thickness = 2;

gcLabel1.ShadowEffect = shadowEffect1;
```

```vbnet
Dim shadowEffect1 As New GrapeCity.Win.Buttons.ShadowEffect()
shadowEffect1.Color = Color.Silver
shadowEffect1.Thickness = 2

GcLabel1.ShadowEffect = shadowEffect1
```

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gclabel.shadoweffect.png)

## テキストの下線／取り消し線／枠線

[TextDecorations](gcdocsite__documentlink?toc-item-id=5101d131-e7cb-4518-bee4-649d684af1e5)クラスを使用すると、テキストに下線／取り消し線／枠線を表示できます。それぞれの線には、線の色と種類を設定することができます。

```csharp
GrapeCity.Win.Buttons.TextDecorations textDecorations1 = new GrapeCity.Win.Buttons.TextDecorations();
textDecorations1.StrikethroughColor = Color.Black;
textDecorations1.StrikethroughStyle = GrapeCity.Win.Buttons.TextLineStyle.Double;
textDecorations1.TextBorderColor = Color.Black;
textDecorations1.TextBorderStyle = GrapeCity.Win.Buttons.TextBorderStyle.DashDot;
textDecorations1.TextBorderWidth = 5;
textDecorations1.UnderlineColor = Color.Black;
textDecorations1.UnderlineStyle = GrapeCity.Win.Buttons.TextLineStyle.Waved;

gcLabel1.TextDecorations = textDecorations1;
```

```vbnet
Dim textDecorations1 As New GrapeCity.Win.Buttons.TextDecorations()
textDecorations1.StrikethroughColor = Color.Black
textDecorations1.StrikethroughStyle = GrapeCity.Win.Buttons.TextLineStyle.Double
textDecorations1.TextBorderColor = Color.Black
textDecorations1.TextBorderStyle = GrapeCity.Win.Buttons.TextBorderStyle.DashDot
textDecorations1.TextBorderWidth = 5
textDecorations1.UnderlineColor = Color.Black
textDecorations1.UnderlineStyle = GrapeCity.Win.Buttons.TextLineStyle.Waved

GcLabel1.TextDecorations = textDecorations1
```

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gclabel.textdecorations.png)

## コントロール無効時のスタイル

コントロールのEnabledプロパティがFalseに設定されている場合、コントロールは無効となり背景や文字がグレーで表示されますが、[DisabledForeColor](gcdocsite__documentlink?toc-item-id=9454c650-dd78-4aa8-bc62-6cc3c98deaa2)プロパティで無効時の文字色を指定することができます。

```csharp
gcLabel1.DisabledForeColor = Color.Red;
```

```vbnet
GcLabel1.DisabledForeColor = Color.Red
```

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gclabel.disabledforecolor.png)

## 関連トピック

[GcLabelコントロール](gcdocsite__documentlink?toc-item-id=40f5c3ca-e4f8-47ac-aff9-746a680da7a3)
[ラベルスタイルの設定](gcdocsite__documentlink?toc-item-id=952b7d9e-cb57-4f01-82bd-e3f858e59060)
[文字の表示幅の設定](gcdocsite__documentlink?toc-item-id=436a3936-92db-4b27-a5aa-df2da1f57a49)
[縦表示文字の設定](gcdocsite__documentlink?toc-item-id=2c5593c8-843b-4d41-adc8-9eb2b4b8debe)