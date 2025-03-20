セルの左右両端にはサイドボタンとして自由にボタンを配置し機能を割り付けることができます。
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/sidebuttons.png)

## ボタンの種類

セルには次の4種類のボタンオブジェクトを追加できます。

#### [DropDownButton](gcdocsite__documentlink?toc-item-id=a9a24bf8-9fde-41f4-ab5c-41d79362e53c) （ドロップダウンボタン）

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/sidebutton_dropdown.png)
下向きの矢印が描かれたボタンです。主にドロップダウンウィンドウを表示するために用いられます。GcDateTimeCellでは、ドロップダウンカレンダーまたはドロップダウン日付時刻ピッカーが表示可能です。ドロップダウンの動作は、[DropDown](gcdocsite__documentlink?toc-item-id=56521e17-4d8f-4623-ba64-c74be67587b9)プロパティが参照する[DateTimeDropDown](gcdocsite__documentlink?toc-item-id=fffb88b9-a03e-4327-a6e3-9b282ac4ec38)クラスにより次のようなプロパティを設定できます。

* [AllowDrop](gcdocsite__documentlink?toc-item-id=d53cbeba-b7ea-4859-9bf1-6d80247ae490)プロパティ（ドロップダウンを許可するかどうか）
* [AllowResize](gcdocsite__documentlink?toc-item-id=cd8bafb2-dd61-4c20-969a-dade900e7df0)プロパティ（ウィンドウのサイズ変更を許可するかどうか）
* [AutoDropDown](gcdocsite__documentlink?toc-item-id=dd10ef3f-6b54-4d33-a14c-fe0548d521cc)プロパティ（フォーカス取得時に自動でドロップダウンを表示するかどうか）
* [AutoHideTouchKeyboard](gcdocsite__documentlink?toc-item-id=c7e2647a-78f2-4c13-8bea-b53981215050)プロパティ（ドロップダウンが開かれたときタッチキーボードを非表示にするかどうか）
* [ClosingAnimation](gcdocsite__documentlink?toc-item-id=7312b171-8733-4a94-9b69-1d1198676dda)プロパティ（ドロップダウンウィンドウを閉じる時のアニメーション）
* [Direction](gcdocsite__documentlink?toc-item-id=421ed70c-f3c4-4c60-a4e6-d72708ce8fcc)プロパティ（ドロップダウンウィンドウを表示する方向）
* [DropDownType](gcdocsite__documentlink?toc-item-id=dc74a1d2-db4f-4489-a6f5-109fe555d45e)プロパティ（ドロップダウン表示するオブジェクト）
* [OpeningAnimation](gcdocsite__documentlink?toc-item-id=26c81315-b95f-422c-b833-c170e0ef3311)プロパティ（ドロップダウンウィンドウを開く時のアニメーション）
* [ShowShadow](gcdocsite__documentlink?toc-item-id=1d0073d2-2712-4117-8aa2-f634a8d40dd0)プロパティ（ドロップダウンウィンドウに影を表示するかどうか）

#### [SpinButton](gcdocsite__documentlink?toc-item-id=464b6fcd-78a3-4e4a-b4f7-bd226c58778b) （スピンボタン）

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/sidebutton_spin.png)
上下それぞれに矢印が描かれた２つのボタンが組み合わされたボタンです。主にセル内の値を増減するために用いられます。
GcDateTimeCellでは、[Spin](gcdocsite__documentlink?toc-item-id=2270dbc1-d8aa-4f31-9893-fda01345e20b)プロパティが参照する[DateSpin](gcdocsite__documentlink?toc-item-id=0960f280-a82f-4509-8663-931e2781998c)クラスにより、スピン機能の動作を設定することができます。

* [AllowSpin](gcdocsite__documentlink?toc-item-id=84b3e4b9-8eb3-4ef8-921e-5402c50424dd)プロパティ（スピン機能を有効にするかどうか設定します。）
* [Increment](gcdocsite__documentlink?toc-item-id=151b5bba-4122-4ef7-9a06-798ebd5efbe0)プロパティ（スピン時のフィールドの値の増減量を設定します。）
* [IncrementValue](gcdocsite__documentlink?toc-item-id=b689e070-fb53-4466-a6da-636e7a91ad0f)プロパティ（スピンアクション時の値の増減量を設定します。）
* [SpinMode](gcdocsite__documentlink?toc-item-id=33bb8e7e-1cee-4fc4-956e-bbbb91d83ec7)プロパティ（アクティブなフィールドの値かセルの値を増減するかを設定します。）
* [SpinOnKeys](gcdocsite__documentlink?toc-item-id=57c53294-cdbc-4e65-a4cf-d584810de03c)プロパティ（キーの押下によって値の増減を行うかどうか設定します。）
* [SpinOnWheel](gcdocsite__documentlink?toc-item-id=1466eb87-f8b6-4a24-b509-da2b1d1d1dcb)プロパティ（マウスのホイールによって値の増減やドロップダウンカレンダーの変更を行うかどうか設定します。）
* [Wrap](gcdocsite__documentlink?toc-item-id=382d60fe-72d7-4e8a-80b9-29ba3daf01ad)プロパティ（スピン時に値の増減を有効範囲内でループさせるかどうか設定します。）

#### [SideButton](gcdocsite__documentlink?toc-item-id=bfcad2b7-744a-4806-8acb-c318b1372987) （サイドボタン）

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/sidebutton_side.png)
標準のButtonコントロールと同じような外観を持つボタンです。ボタン上にはイメージとテキストを設定することができます。
また、[CheckOnClick](gcdocsite__documentlink?toc-item-id=89de75ee-faf3-4719-a0bd-a7ab1bc0e962)プロパティを使用するとチェックボタンとして機能させることもできます。

#### [SymbolButton](gcdocsite__documentlink?toc-item-id=abff72a6-6957-47c3-9c97-6f625b15ef8a) （シンボルボタン）

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/sidebutton_symbol.png)
SideButtonと同様、標準のButtonコントロールと似た外観を持ちますが、提供されたイメージの中からボタン上に表示する画像を設定することができます。イメージは、[Symbol](gcdocsite__documentlink?toc-item-id=88ac9a40-bd01-49bd-a344-555cfc7c8d36)プロパティを使用して設定し、[SymbolDirection](gcdocsite__documentlink?toc-item-id=fd81fa3d-cbfd-4751-8b70-e2d2ffc55957)プロパティを使用してイメージの向きを設定することができます。
シンボルボタンにはテキストは表示できません。

## ボタンの追加と削除

#### コードによる設定

セルにボタンを追加するには、[SideButtons](gcdocsite__documentlink?toc-item-id=3f8fc905-b83c-4e52-bc13-522296ac9731)プロパティが参照する[SideButtonCollection](gcdocsite__documentlink?toc-item-id=0adb81b6-e6b7-449e-bed8-dd7d48259da2)クラスの[Add](gcdocsite__documentlink?toc-item-id=0f0fd190-756c-41f7-bff3-7cfbb6a8bd7d)または[AddRange](gcdocsite__documentlink?toc-item-id=03c7c770-d785-447f-bc30-94e61de916fa)メソッドを使用します。SideButtonCollectionクラスは、セルに追加するボタンオブジェクトのコレクションで、セルに追加可能なサイドボタンを追加、削除するためのメソッドを提供します。
以下は、Addメソッドを使用してGcDateTimeCellにスピンボタンを追加する例です。

```csharp
using GrapeCity.Win.MultiRow;
using InputManCell = GrapeCity.Win.MultiRow.InputMan;

InputManCell.GcDateTimeCell gcDateTimeCell1 = new InputManCell.GcDateTimeCell();
gcDateTimeCell1.Name = "gcDateTimeCell1";
// スピンボタンを追加  
gcDateTimeCell1.SideButtons.Add(new InputManCell.SpinButton());
gcMultiRow1.Template = Template.CreateGridTemplate(new Cell[] { gcDateTimeCell1 });
```

```vbnet
Imports GrapeCity.Win.MultiRow
Imports InputManCell = GrapeCity.Win.MultiRow.InputMan

Dim GcDateTimeCell1 As New InputManCell.GcDateTimeCell()
GcDateTimeCell1.Name = "GcDateTimeCell1"
' スピンボタンを追加  
GcDateTimeCell1.SideButtons.Add(New InputManCell.SpinButton())
GcMultiRow1.Template = Template.CreateGridTemplate(New Cell() {GcDateTimeCell1})
```

また、追加したボタンオブジェクトの[Parent](gcdocsite__documentlink?toc-item-id=07e6513d-794e-4a58-a0cd-1b29d7fdf9c3)プロパティからは、ボタンが追加されたセルのオブジェクトを取得することができます。
追加したボタンを削除するには、SideButtonCollectionクラスの[Remove](gcdocsite__documentlink?toc-item-id=9e4388a0-a728-436b-b812-c556b97d3a83)メソッドまたは、[RemoveAt](gcdocsite__documentlink?toc-item-id=d5818c36-dc8a-490b-a7f1-dae502de0d95)メソッドを使用します。また、Clearメソッドでコレクションに追加されたすべてのボタンをクリアすることができます。
次のコードは、RemoveAtメソッドを使用してコレクションの先頭に追加されたボタンを削除する例です。
このサンプルでは、テンプレートのRowセクションに[gcDateTimeCell1]が配置されていることを前提とします。

```csharp
using InputManCell = GrapeCity.Win.MultiRow.InputMan;

InputManCell.GcDateTimeCell gcDateTimeCell = (InputManCell.GcDateTimeCell)gcMultiRow1.CurrentRow.Cells["gcDateTimeCell1"];

// コレクションの先頭のボタンを削除  
if (gcDateTimeCell.SideButtons.Count > 0)
{
    gcDateTimeCell.SideButtons.RemoveAt(0);
}
```

```vbnet
Imports InputManCell = GrapeCity.Win.MultiRow.InputMan

Dim GcDateTimeCell As InputManCell.GcDateTimeCell =
    DirectCast(GcMultiRow1.CurrentRow.Cells("GcDateTimeCell1"), InputManCell.GcDateTimeCell)

' コレクションの先頭のボタンを削除  
If GcDateTimeCell.SideButtons.Count > 0 Then
    GcDateTimeCell.SideButtons.RemoveAt(0)
End If
```

#### デザイン画面での設定

デザイン画面ではサイドボタンの追加や削除ができる「サイドボタンの編集」エディタから容易な設定が可能です。 このエディタは次のいずれかの方法で起動でき、GcDateTimeCellに追加するサイドボタンを設定できます。

* セルのスマート タグから「サイドボタンの編集...」を選択
* プロパティウィンドウのSideButtonsプロパティをアクティブした時に表示される「…」ボタンを押下

## ドロップダウン動作の割り当て

GcDateTimeCellには、以下の２つのドロップダウンオブジェクトが表示可能です。

* [ドロップダウンカレンダー](gcdocsite__documentlink?toc-item-id=636ed515-d9bd-4cd4-95e1-a248269ffe78)
* [ドロップダウン日付時刻ピッカー](gcdocsite__documentlink?toc-item-id=bba04be6-e380-412d-8f5d-f5fa1d59e4f0)

どちらのドロップダウンオブジェクトを表示するかを設定するには、[DropDown](gcdocsite__documentlink?toc-item-id=725b3f4a-a92c-4a8a-932a-e29fb17ce0ad)プロパティが参照する[DateTimeDropDown](gcdocsite__documentlink?toc-item-id=fffb88b9-a03e-4327-a6e3-9b282ac4ec38)クラスの[DropDownType](gcdocsite__documentlink?toc-item-id=dc74a1d2-db4f-4489-a6f5-109fe555d45e)プロパティを使用します。既定値は、[DateDropDownType.Calendar](gcdocsite__documentlink?toc-item-id=767c940e-dd0c-44f1-a0a0-ab34d2e836ad)です。
次のサンプルコードは、ドロップダウンオブジェクトとして、日付時刻ピッカーを設定する方法を示します。

```csharp
using GrapeCity.Win.MultiRow;
using InputManCell = GrapeCity.Win.MultiRow.InputMan;

InputManCell.GcDateTimeCell gcDateTimeCell1 = new InputManCell.GcDateTimeCell();

// サイドボタンにドロップダウンボタンを追加します。
gcDateTimeCell1.SideButtons.Add(new InputManCell.DropDownButton());
// ドロップダウンオブジェクトに日付時刻ピッカーを設定します。
gcDateTimeCell1.DropDown.DropDownType = GrapeCity.Win.Editors.DateDropDownType.Picker;

gcMultiRow1.Template = Template.CreateGridTemplate(new Cell[] { gcDateTimeCell1 });
gcMultiRow1.RowCount = 5;
```

```vbnet
Imports GrapeCity.Win.MultiRow
Imports InputManCell = GrapeCity.Win.MultiRow.InputMan
                                                                
Dim GcDateTimeCell1 = New InputManCell.GcDateTimeCell()

' サイドボタンにドロップダウンボタンを追加します。
GcDateTimeCell1.SideButtons.Add(New InputManCell.DropDownButton())
' ドロップダウンオブジェクトに日付時刻ピッカーを設定します。
GcDateTimeCell1.DropDown.DropDownType = GrapeCity.Win.Editors.DateDropDownType.Picker

' MultiRowのテンプレートを設定します。  
GcMultiRow1.Template = Template.CreateGridTemplate(New Cell() {GcDateTimeCell1})
GcMultiRow1.RowCount = 5
```

なお、ドロップダウンオブジェクトを表示するには、次の4つの方法があります。

* ドロップダウンボタンをクリック
* キーボードで［Alt＋↓］キーまたは［F4］キーを押下
* GcDateTimeEditingControl.Dropメソッドを実行

[AutoHideTouchKeyboard](gcdocsite__documentlink?toc-item-id=c7e2647a-78f2-4c13-8bea-b53981215050)プロパティを使用すると、ドロップダウンオブジェクトがタッチキーボードの背面に隠れないよう、タッチキーボードを自動的に非表示にすることができます。

## スピン動作の割り当て

サイドボタンおよびシンボルボタンには、プロパティの設定によりスピン動作の機能を割り当てることができます。

#### サイドボタンへのスピン動作の割り当て

[SideButton](gcdocsite__documentlink?toc-item-id=bfcad2b7-744a-4806-8acb-c318b1372987)クラスは、サイドボタンにスピン動作を割り当てる[Behavior](gcdocsite__documentlink?toc-item-id=3cc56dc6-b981-4d61-b598-6af44aff908f)プロパティを提供します。また、Behaviorプロパティに設定した値により、[Interval](gcdocsite__documentlink?toc-item-id=5d9d1561-a44b-4c57-8bad-13de72d5272a)プロパティと[Text](gcdocsite__documentlink?toc-item-id=0b5e7009-836e-4633-b89b-44274e1c76c4)プロパティの初期値が自動的に変更されます。
Behaviorプロパティに設定可能な値は以下の通りです。

| Behaviorの値 | 説明 | Intervalプロパティの初期値 | Textプロパティの初期値 |
| ---------- | --- | ----------------- | ------------- |
| None | スピン動作を割り当てません。 | 0 | なし |
| SpinUp | スピンアップ（値を増加）の動作を割り当てます。 | 60 | "+" |
| SpinDown | スピンダウン（値を減少）の動作を割り当てます。 | 60 | "-" |

サイドボタンに割り当てられるスピン機能の詳細については「[スピンボタンの最適化](gcdocsite__documentlink?toc-item-id=f6161938-3039-43bd-8ee6-b4f969398cca)」を参照してください。

#### シンボルボタンへのスピン動作の割り当て

[SymbolButton](gcdocsite__documentlink?toc-item-id=abff72a6-6957-47c3-9c97-6f625b15ef8a)クラスは、サイドボタンにスピン動作を割り当てる[Behavior](gcdocsite__documentlink?toc-item-id=eac818c4-7374-4918-955f-8181dbe00b1e)プロパティを提供します。また、Behaviorプロパティに設定した値により、[Interval](gcdocsite__documentlink?toc-item-id=8bd09a3b-b361-4bea-8a9f-53526f9081ac)プロパティ、[Symbol](gcdocsite__documentlink?toc-item-id=88ac9a40-bd01-49bd-a344-555cfc7c8d36)プロパティおよび[SymbolDirection](gcdocsite__documentlink?toc-item-id=fd81fa3d-cbfd-4751-8b70-e2d2ffc55957)プロパティの初期値が自動的に変更されます。
Behaviorプロパティに設定可能な値は以下の通りです。

| Behaviorの値 | 説明 | Intervalプロパティの初期値 | Symbolプロパティの初期値 | SymbolDirectionプロパティの初期値 |
| ---------- | --- | ----------------- | --------------- | ------------------------ |
| None | スピン動作を割り当てません。 | 0 | None | Left |
| SpinUp | スピンアップ（値を増加）の動作を割り当てます。 | 60 | Arrow | Up |
| SpinDown | スピンダウン（値を減少）の動作を割り当てます。 | 60 | Arrow | Down |

シンボルボタンに割り当てられるスピン機能の詳細については「[スピンボタンの最適化](gcdocsite__documentlink?toc-item-id=f6161938-3039-43bd-8ee6-b4f969398cca)」を参照してください。

## 外観の変更

各ボタンオブジェクトの[Position](gcdocsite__documentlink?toc-item-id=f434cb81-bcea-4efd-8d81-ad79cc74d8e2)プロパティを使用するとボタンの表示位置を設定することができます。
それぞれの位置でのボタンの並びはコレクション内のインデックスによって決定されます。コレクション内のインデックスが小さい順に左から右へボタンが配置されます。
ボタンのサイズはセルの高さと各ボタンオブジェクトのWidthプロパティによって設定されます。
サイドボタンの背景色は各ボタンオブジェクトの[BackColor](gcdocsite__documentlink?toc-item-id=2767692f-9d4b-4706-8540-8d2c90fd2e84)プロパティで、前景色は[ForeColor](gcdocsite__documentlink?toc-item-id=e18fae3c-03ca-4852-9a35-a7c532bd4656)プロパティで設定します。背景色と前景色はセルのFlatStyleプロパティがFlat、およびPopupの場合のみ有効となります。
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/sidebutton_flat.png)
(図) FlatStyle プロパティがFlatの場合
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/sidebutton_popup.png)
(図) FlatStyle プロパティがPopupの場合

## 関連トピック

[GcDateTimeCell](gcdocsite__documentlink?toc-item-id=b80001db-fab9-48f7-baab-a639554c60a2)
[入力の制御](gcdocsite__documentlink?toc-item-id=6564107e-1f0b-4a35-bd8e-059b15c79f37)
[書式の設定](gcdocsite__documentlink?toc-item-id=7af683d1-49d4-4662-8d5c-ff95be53c699)
[視覚的な補助](gcdocsite__documentlink?toc-item-id=9d947385-bd2c-4754-beba-489cbdd8b536)
[ドロップダウンカレンダー](gcdocsite__documentlink?toc-item-id=636ed515-d9bd-4cd4-95e1-a248269ffe78)
[ドロップダウン日付時刻ピッカー](gcdocsite__documentlink?toc-item-id=bba04be6-e380-412d-8f5d-f5fa1d59e4f0)
[外観の設定](gcdocsite__documentlink?toc-item-id=d2ac536f-45ed-4239-b020-0a46fa9baa14)
[和暦表示の設定](gcdocsite__documentlink?toc-item-id=346274df-ba85-4704-94de-81503622da40)
[データベース接続](gcdocsite__documentlink?toc-item-id=88836a36-6f2a-4e07-9825-e71e0993bf66)