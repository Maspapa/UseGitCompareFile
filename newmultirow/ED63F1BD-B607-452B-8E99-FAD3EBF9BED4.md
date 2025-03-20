ここでは、キーワードによる書式設定について説明します。

## 概要

GcNumberCellでは、数値のキーワードを設定することで書式を設定することができます。フィールドオブジェクトによる書式設定のように柔軟なスタイル設定が不要な場合、入力および表示書式についてそれぞれ1度のメソッド実行だけで定義できるため、簡単な実装が可能です。

> !type=warning
> キーワードによる書式設定は、El Tabelle MultiRow 4.0J の数値型セルと同様の方法です。

## 設定方法

#### コードによる設定

入力書式を設定するには、[Fields](gcdocsite__documentlink?toc-item-id=59ee44d4-d1df-4b91-bd80-ce221347deac)プロパティが参照する[NumberFields](gcdocsite__documentlink?toc-item-id=50efb0e6-fe28-4c06-80f0-c6b50622961d)クラスの[SetFields](gcdocsite__documentlink?toc-item-id=01eb3f91-7861-44be-b394-97ba40862074)メソッドに、入力書式用のキーワードを使用した文字列を設定します。
表示書式を設定するには、[DisyplayFields](gcdocsite__documentlink?toc-item-id=3e4f2641-6daa-42c2-bbc8-267be5f15db5)プロパティが参照する[NumberDisplayFieldCollection](gcdocsite__documentlink?toc-item-id=4afdb7ae-a0c3-4cd9-b60f-265870d3577d)クラスの[AddRange](gcdocsite__documentlink?toc-item-id=495f85a2-bfc0-4e5a-ae1e-981fd6000be0)メソッドに、表示書式用のキーワードを使用した文字列を設定します。
キーワードは文字列として次の順番で定義します。

```auto
Pattern, positive prefix, positive suffix, negative prefix, negattive suffix
```

```csharp
using GrapeCity.Win.MultiRow;
using InputManCell = GrapeCity.Win.MultiRow.InputMan;

InputManCell.GcNumberCell gcNumberCell1 = new InputManCell.GcNumberCell();

// キーワードから書式を設定します。
gcNumberCell1.Fields.SetFields("####0.00,,,-,");
gcNumberCell1.DisplayFields.AddRange("####0.00,,,-,");

gcMultiRow1.Template = Template.CreateGridTemplate(new Cell[] { gcNumberCell1 });
```

```vbnet
Imports GrapeCity.Win.MultiRow
Imports InputManCell = GrapeCity.Win.MultiRow.InputMan

Dim GcNumberCell1 = New InputManCell.GcNumberCell()

' フィールドをクリアします。  
GcNumberCell1.DisplayFields.Clear()

' キーワードから書式を設定します。 
GcNumberCell1.Fields.SetFields("####0.00,,,-,")
GcNumberCell1.DisplayFields.AddRange("####0.00,,,-,")

GcMultiRow1.Template = Template.CreateGridTemplate(New Cell() {GcNumberCell1})
```

なお、AddRangeメソッドにより書式を設定する場合でも、自動的にフィールドオブジェクトに変換されているため、設定後に特定のフィールドスタイルを変更することが可能です。
次のサンプルコードは、キーワードにより設定した数値書式で特定のフィールドのスタイルを設定する例です。

```csharp
// 入力書式フィールドのスタイルを設定します。
gcNumberCell1.Fields[0].BackColor = Color.Bisque;
gcNumberCell1.Fields[1].ForeColor = Color.DarkGray;
gcNumberCell1.Fields[2].Font = new Font("Meiryo UI", 12);

// 表示書式フィールドのスタイルを設定します。
gcNumberCell1.DisplayFields[0].Font = new Font("ＭＳ ゴシック", 15);
gcNumberCell1.DisplayFields[1].BackColor = Color.Yellow;
gcNumberCell1.DisplayFields[2].ForeColor = Color.Gray;
```

```vbnet
' 入力書式フィールドのスタイルを設定します。
GcNumberCell1.Fields(0).BackColor = Color.Bisque
GcNumberCell1.Fields(1).ForeColor = Color.DarkGray
GcNumberCell1.Fields(2).Font = New Font("Meiryo UI", 12)

' 表示書式フィールドのスタイルを設定します。
GcNumberCell1.DisplayFields(0).Font = New Font("ＭＳ ゴシック", 15)
GcNumberCell1.DisplayFields(1).BackColor = Color.Yellow
GcNumberCell1.DisplayFields(2).ForeColor = Color.Gray
```

#### デザイン画面での設定

デザイン画面では「入力書式の設定」「表示書式の設定」エディタを使用して容易な設定が可能です。これらのエディタは次のいずれかの方法で起動でき、数値のキーワードを設定することで書式を作成します。
入力書式

* セルのスマート タグから「入力書式の設定...」を選択

表示書式

* セルのスマート タグから「表示書式の設定...」を選択

個々のフィールドのプロパティは設定できませんが、桁区切りや漢数字などの書式が予めビルトイン書式として用意されているため、これらのリストから書式を選択するだけで簡単に書式を定義することが可能です。

## 入力書式のキーワード

入力書式として使用可能なキーワードは以下のとおりです。

| キーワード | 説明 |
| ----- | --- |
| # | 数値の桁を指定します。値が0の場合は何も表示されません。 |
| 0 | 数値の桁を指定します。値が0の場合は0を表示します。 |
| .（ピリオド） | 小数点の挿入位置を指定します。キーワード内に含められるのは１つだけです。 |
| ,（カンマ） | カンマの挿入位置を指定します。少数部に指定することはできません。 |

## 表示書式のキーワード

表示書式として使用可能なキーワードは以下のとおりです。

| キーワード | 説明 |
| ----- | --- |
| # | 数値の桁を指定します。値が0の場合は何も表示されません。 |
| 0 | 数値の桁を指定します。値が0の場合は0を表示します。 |
| .（ピリオド） | 小数点の挿入位置を指定します。キーワード内に含められるのは１つだけです。 |
| ,（カンマ） | カンマの挿入位置を指定します。少数部に指定することはできません。 |
| [DBNum1]G | 数値を漢数字で表示します。（例：一億二千三百四十五万六千七百八十九） |
| [DBNum2]G | 数字を漢数字（大字）で表示します。（例：壱億弐阡参百四拾伍萬六阡七百八拾九） |
| [DBNum3]G | 数字を漢数字と全角の数字を組み合わせて表示します。（例：１億２千３百４十５万６千７百８十９） |
| [DBNum4]G | 小数点以下の数字を漢数字を使って表示します。（例：〇.九分八厘七毛六糸五忽四微三纖二沙一塵） |
| [:] | [###:千]のように使用します。コロンの前に記載した桁数をコロンの後に記載した文字列に置き換えます。（例：1,234千円） |

## 関連トピック

[GcNumberCell](gcdocsite__documentlink?toc-item-id=d4ea9511-22bf-4df0-8ebf-c6d2440ae435)
[書式の設定](gcdocsite__documentlink?toc-item-id=7028825f-0cf6-4118-b0f9-ef931199983c)
[フィールドオブジェクトによる書式設定](gcdocsite__documentlink?toc-item-id=e1fd45fe-22c5-449f-8d9e-6b28a771e58c)