リストボックス部の項目のスタイル、サブアイテムのスタイル等について説明します。ヘッダのスタイルについては「[ヘッダの設定](gcdocsite__documentlink?toc-item-id=f10714ed-1615-447f-9494-64690b2c1f29)」を参照してください。

## 項目スタイル

リストボックス内に表示されている項目のスタイルは、項目（行）ごとにスタイルを定義することができます。
項目にスタイルを定義するには、リスト内の個々の項目を表す[ListItem](gcdocsite__documentlink?toc-item-id=2f9292a1-5e58-4386-b874-241f139daa85)のオブジェクトを使用して、個別にスタイル定義することもできますが、[ListItemTemplates](gcdocsite__documentlink?toc-item-id=efcda4e0-46ca-4f8e-94c0-9b11ef7a8c60)プロパティを使用すれば、リストボックス全体に一貫したスタイルを適用することができるため便利です。ItemTemplatesプロパティを使うと下図のように、複数のスタイルを特定の行おきに繰り返して表示することができます。
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/08gccombobox/gccombobox_itemtemplates.png)
ItemTemplatesプロパティは、[ItemTemplateCollection](gcdocsite__documentlink?toc-item-id=16294b1c-f004-49a6-a8c1-028407a2b889)オブジェクトを参照します。ItemTemplateCollection オブジェクトは、 項目のスタイルを定義する[ItemTemplate](gcdocsite__documentlink?toc-item-id=79754301-0a45-4fd8-92d1-7cde47248dae)オブジェクトを格納するコレクションです。
スタイルの繰り返しの数は、ItemTemplateCollectionに追加されたItemTemplateオブジェクトの数で決定されます。つまり、コレクションに１つのオブジェクトが格納されている場合は、1つのスタイルが毎行繰り返されるため、リストボックス内の項目のすべてが同じスタイルになります。コレクションにオブジェクトが2つ格納されている場合は、1行おき項目のスタイルが繰り返されるようになります。
ItemTemplate オブジェクトでは、スタイルや外観の設定に関して次のプロパティを持っています。

* [AutoItemHeight](gcdocsite__documentlink?toc-item-id=b0df6487-1ec7-496a-997b-57609d9c2ba6)（項目の高さを自動設定します。）
* [BackColor](gcdocsite__documentlink?toc-item-id=4f1bbd3d-abaa-49a0-9ffb-301bd91e7d36)（背景色を設定します。）
* [Font](gcdocsite__documentlink?toc-item-id=30e5fc98-b215-4409-bf08-264806a85337)（フォントを設定します。）
* [ForeColor](gcdocsite__documentlink?toc-item-id=8050633a-bbb3-4c46-af28-d3fba1604150)（前景色を設定します。）
* [GradientEffect](gcdocsite__documentlink?toc-item-id=ca3b24aa-6a6c-4d77-a3be-27ef3dc40205)（グラデーション効果を設定します。）
* [Height](gcdocsite__documentlink?toc-item-id=676eabbc-49b9-4df2-8934-52cd20354599)（項目の高さを設定します。）
* [Image](gcdocsite__documentlink?toc-item-id=22bd7e5b-7fe9-419b-b1f4-dfcb978a1f7d)（項目の先頭カラムに表示する画像を設定します。）
* [Indent](gcdocsite__documentlink?toc-item-id=27f5a837-7efd-4099-beec-3cb302121674)（セル左端からのインデントの距離を設定します。）

次のサンプルは、1行おきに項目のスタイルを設定する例です。

```csharp
using GrapeCity.Win.MultiRow;
using InputManCell = GrapeCity.Win.MultiRow.InputMan;

InputManCell.GcComboBoxCell gcComboBoxCell1 = new InputManCell.GcComboBoxCell();

// ヘッダを非表示にします。 
gcComboBoxCell1.ListHeaderPane.Visible = false;

// GcComboBoxCell に項目を追加 
gcComboBoxCell1.Items.AddRange(new InputManCell.ListItem[] { 
    new InputManCell.ListItem("Sunday"), new InputManCell.ListItem("Monday"), 
    new InputManCell.ListItem("Tuesday"), new InputManCell.ListItem("Wednesday"),
    new InputManCell.ListItem("Thursday"), new InputManCell.ListItem("Friday"),
    new InputManCell.ListItem("Saturday")
});

// 項目のスタイルを作成 
InputManCell.ItemTemplate myItemTemp1 = new InputManCell.ItemTemplate(0, null, Color.Silver, Color.Black, 0, new Font("ＭＳ ゴシック", 9), null);
InputManCell.ItemTemplate myItemTemp2 = new InputManCell.ItemTemplate(0, null, Color.Black, Color.White, 0, new Font("ＭＳ ゴシック", 9), null);

// スタイルをテンプレートに設定 
gcComboBoxCell1.ListItemTemplates.Add(myItemTemp1);
gcComboBoxCell1.ListItemTemplates.Add(myItemTemp2);

gcMultiRow1.Template = Template.CreateGridTemplate(new Cell[] { gcComboBoxCell1 });
```

```vbnet
Imports GrapeCity.Win.MultiRow
Imports InputManCell = GrapeCity.Win.MultiRow.InputMan

Dim GcComboBoxCell1 = New InputManCell.GcComboBoxCell()

' ヘッダを非表示にします。 
GcComboBoxCell1.ListHeaderPane.Visible = False

' GcComboBoxCell に項目を追加 
GcComboBoxCell1.Items.AddRange(New InputManCell.ListItem() { _
    New InputManCell.ListItem("Sunday"), New InputManCell.ListItem("Monday"), _
    New InputManCell.ListItem("Tuesday"), New InputManCell.ListItem("Wednesday"), _
    New InputManCell.ListItem("Thursday"), New InputManCell.ListItem("Friday"), _
    New InputManCell.ListItem("Saturday") _
})

' 項目のスタイルを作成 
Dim myItemTemp1 As New InputManCell.ItemTemplate(0, Nothing, Color.Silver, Color.Black, 0, New Font("ＭＳ ゴシック", 9), Nothing)
Dim myItemTemp2 As New InputManCell.ItemTemplate(0, Nothing, Color.Black, Color.White, 0, New Font("ＭＳ ゴシック", 9), Nothing)

' スタイルをテンプレートに設定 
GcComboBoxCell1.ListItemTemplates.Add(myItemTemp1)
GcComboBoxCell1.ListItemTemplates.Add(myItemTemp2)

GcMultiRow1.Template = Template.CreateGridTemplate(New Cell() {GcComboBoxCell1})
```

なお、デザイン画面では項目のスタイルを設定する専用のエディタ「項目スタイルの既定値の設定」から容易な設定が可能です。 このエディタは次の方法で起動できます。

* プロパティウィンドウのListItemTemplates プロパティをアクティブした時に表示される「…」ボタンを押下

また、GcComboBoxCellは、プリセットとして予め定義されたスタイルテンプレートを使って項目や交互行のスタイルを定義することができます。 スタイルテンプレートから選択したスタイルは、自動的に項目スタイルに変換され「項目スタイルの既定値の設定」エディタで再編集することも可能です。スタイルテンプレートは次の方法で起動できます。

* セルのスマート タグから「テンプレート...」を選択

## グリッド線

[ListGridLines](gcdocsite__documentlink?toc-item-id=d1b94fc2-2c13-4c98-a832-0bea7fc69b8a)プロパティを使用して、水平方向および垂直方向のグリッド線を設定できます。ListGridLinesプロパティは[ListGridLines](gcdocsite__documentlink?toc-item-id=d0a6eac4-1868-4dd3-9825-a5f0fe3123c9)クラスを参照し、このクラスの[HorizontalLines](gcdocsite__documentlink?toc-item-id=4bab86f2-33c4-47b9-a79e-64963da0f6e3)プロパティは水平方向のグリッド線を、[VerticalLines](gcdocsite__documentlink?toc-item-id=ec01338c-ab8b-42b9-9ffa-413fae503f52)プロパティは垂直方向のグリッド線を設定します。
これらのプロパティは[Line](gcdocsite__documentlink?toc-item-id=4b95ec84-0b59-4965-9d2f-6dd16a491fcb)クラスを参照し、色や幅、線種などを設定することができます。
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/08gccombobox/gclistbox_gridline.png)

## 状態ごとの外観

リストボックスの項目は、選択されている状態と無効な状態のときのスタイルを個別に設定することができます。
選択行のスタイルを設定するには、[ListSelectedItemStyle](gcdocsite__documentlink?toc-item-id=a5ab67c6-5326-44d5-a934-efff045975ec)プロパティを使用します。
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/08gccombobox/gccombobox_selecteditem.png)
また、項目を定義する[ListItem](gcdocsite__documentlink?toc-item-id=2f9292a1-5e58-4386-b874-241f139daa85)オブジェクトの[Enabled](gcdocsite__documentlink?toc-item-id=c5029546-664c-4a2e-a247-506a1c932fd1)プロパティがFalseに設定され、選択できず無効な項目のスタイルは[ListDisabledItemStyle](gcdocsite__documentlink?toc-item-id=82e34b38-68ee-41b8-810f-1e78a37578c3)プロパティを使用します。いずれも[ItemStyle](gcdocsite__documentlink?toc-item-id=dfd972a2-336a-4a0d-bbd6-af8517b9f76d)クラスを参照し以下のプロパティを持ちます。

* [BackColor](gcdocsite__documentlink?toc-item-id=22461b6d-500f-4f81-aac1-32f14ab96f4f)（背景色を設定します。）
* [ForeColor](gcdocsite__documentlink?toc-item-id=89870cb4-b169-4086-b629-ebe7c73d95ae)（前景色を設定します。）
* [GradientEffect](gcdocsite__documentlink?toc-item-id=300b4456-cc0f-41d1-a64a-c44befd079f2)（グラデーション効果を設定します。）

次のサンプルは、選択項目と無効な項目のスタイルを設定する例です。

```csharp
using GrapeCity.Win.MultiRow;
using InputManCell = GrapeCity.Win.MultiRow.InputMan;

InputManCell.GcComboBoxCell gcComboBoxCell1 = new InputManCell.GcComboBoxCell();

// ヘッダを非表示にします。
gcComboBoxCell1.ListHeaderPane.Visible = false;

// コンボコントロールに項目を追加します。
gcComboBoxCell1.Items.AddRange(new InputManCell.ListItem[] { 
    new InputManCell.ListItem("Sunday"), new InputManCell.ListItem("Monday"), 
    new InputManCell.ListItem("Tuesday"), new InputManCell.ListItem("Wednesday"),
    new InputManCell.ListItem("Thursday"), new InputManCell.ListItem("Friday"),
    new InputManCell.ListItem("Saturday")
});

// 選択項目の背景色と前景色を設定します。
gcComboBoxCell1.ListSelectedItemStyle.BackColor = Color.SlateBlue;
gcComboBoxCell1.ListSelectedItemStyle.ForeColor = Color.Yellow;

// ３つの項目を無効に設定します。
gcComboBoxCell1.Items[0].Enabled = false;
gcComboBoxCell1.Items[1].Enabled = false;
gcComboBoxCell1.Items[3].Enabled = false;

// 無効な項目のスタイルを設定します。
gcComboBoxCell1.ListDisabledItemStyle.BackColor = Color.Gray;
gcComboBoxCell1.ListDisabledItemStyle.ForeColor = Color.Silver;

gcMultiRow1.Template = Template.CreateGridTemplate(new Cell[] { gcComboBoxCell1 });
```

```vbnet
Imports GrapeCity.Win.MultiRow
Imports InputManCell = GrapeCity.Win.MultiRow.InputMan

Dim GcComboBoxCell1 = New InputManCell.GcComboBoxCell()

' ヘッダを非表示にします。
GcComboBoxCell1.ListHeaderPane.Visible = False

' コンボコントロールに項目を追加します。
GcComboBoxCell1.Items.AddRange(New InputManCell.ListItem() { _
    New InputManCell.ListItem("Sunday"), New InputManCell.ListItem("Monday"), _
    New InputManCell.ListItem("Tuesday"), New InputManCell.ListItem("Wednesday"), _
    New InputManCell.ListItem("Thursday"), New InputManCell.ListItem("Friday"), _
    New InputManCell.ListItem("Saturday") _
})

' 選択項目の背景色と前景色を設定します。
GcComboBoxCell1.ListSelectedItemStyle.BackColor = Color.SlateBlue
GcComboBoxCell1.ListSelectedItemStyle.ForeColor = Color.Yellow

' ３つの項目を無効に設定します。
GcComboBoxCell1.Items(0).Enabled = False
GcComboBoxCell1.Items(1).Enabled = False
GcComboBoxCell1.Items(3).Enabled = False

' 無効な項目のスタイルを設定します。
GcComboBoxCell1.ListDisabledItemStyle.BackColor = Color.Gray
GcComboBoxCell1.ListDisabledItemStyle.ForeColor = Color.Silver

GcMultiRow1.Template = Template.CreateGridTemplate(New Cell() {GcComboBoxCell1})
```

## サブアイテムのスタイル

リストの項目に含まれるサブアイテムを表す[SubItem](gcdocsite__documentlink?toc-item-id=a7244382-714b-4d32-9370-943ffeb410a2)には、テキストの配置位置を設定するプロパティが2つ用意されています。入力領域内でテキストの水平および垂直方向の整列位置を指定するには、[ContentAlignment](gcdocsite__documentlink?toc-item-id=fd99fd97-ce99-48f1-8298-94995d0a36af)プロパティを使用します。また、[Padding](gcdocsite__documentlink?toc-item-id=e3631451-56cf-445a-acc5-ae6205ed7c78)プロパティを使うことで、サブアイテムの上下左右の境界線からデータコンテンツの表示領域までの距離をピクセル単位で調整できます。
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/08gccombobox/contentalignment_padding.png)

## 関連トピック

[GcComboBoxCell](gcdocsite__documentlink?toc-item-id=03be278e-45d6-4e66-b049-a8e10aa1ad13)
[リストボックスの使い方](gcdocsite__documentlink?toc-item-id=eb947170-86b0-4ced-91a3-a3bc426d80f6)
[カラムの設定](gcdocsite__documentlink?toc-item-id=b92f5c40-b0f9-4ffa-a5eb-9b27b1330baa)
[ヘッダの設定](gcdocsite__documentlink?toc-item-id=f10714ed-1615-447f-9494-64690b2c1f29)