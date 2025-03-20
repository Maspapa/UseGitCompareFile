GcCharMaskCellの入力制限の機能について解説します。

## 文字種の制限

GcCharMaskCellでは、入力可能な文字種を[Format](gcdocsite__documentlink?toc-item-id=5b345432-8e85-417f-8588-be6375576dd1)プロパティで制限することができます。Formatプロパティに設定できるキーワードは、次の表のとおりです。また、ここで指定された以外の文字種が入力されると、GcCharMaskEditingControl.InvalidInputイベントが発生します。

| 全角 | 半角 | 説明 |
| --- | --- | --- |
| Ａ | A | 大文字のアルファベット（A～Z） |
| ａ | a | 小文字のアルファベット（a～z） |
| Ｋ | K | カタカナ（促音・拗音の小書き表記あり） |
| Ｎ | N | カタカナ（促音・拗音の小書き表記なし） |
| ９ | 9 | 数字（0～9） |
| ＃ | # | 数字および数字関連記号（0～9、+ - $ % \\ , .） |
| ＠ | @ | 記号（\! " \# $ % & ' \( \) \- = ^ \~ \\ \| @ \` \[ \{ ; \+ : \* \] \} \, < \. \> / ? \_ ｡ ｢ ｣ ､ ･） |
| Ｂ | B | 2進数（0または1） |
| Ｘ | X | 16進数（0～9、A～F） |
| Ｊ | - | ひらがな（促音・拗音の小書き表記あり） |
| Ｇ | - | ひらがな（促音・拗音の小書き表記なし） |
| Ｚ | - | すべての全角文字 |
| Ｄ | - | 2バイト文字(サロゲート ペア文字を除いた全角文字) |
| Ｉ | - | JIS X 0208文字で構成された文字 |
| Ｍ | - | Shift JIS文字で構成された文字 |
| - | H | すべての半角文字 |
| - | ^ | 指定した書式に含まれないすべての文字 |
| - | \\ | エスケープ・シーケンス |

> !type=warning
>
> * GcCharMaskCellではサロゲート ペア文字は入力できません。
> * 半角文字と全角文字は、その文字のShift-JISコードを使って識別されます。

文字種の設定は、デザイン画面からは専用の「書式の設定」エディタを使用して容易に設定できます。このエディタは以下のいずれかの方法で起動します。

* セルのスマート タグから「書式の編集...」を選択
* プロパティウィンドウのFormatプロパティをアクティブした時に表示される「…」ボタンを押下

以下に、入力可能な文字種を設定する具体例を示します。
次のコードは、半角大文字のアルファベット（A～Z）と２進数（0, 1）のみを許可します。

```csharp
using GrapeCity.Win.MultiRow;
using InputManCell = GrapeCity.Win.MultiRow.InputMan;

InputManCell.GcCharMaskCell gcCharMaskCell1 = new InputManCell.GcCharMaskCell();
gcCharMaskCell1.Name = "gcCharMaskCell1";
gcCharMaskCell1.Format = "AB";

gcMultiRow1.Template = Template.CreateGridTemplate(new Cell[] { gcCharMaskCell1 });
```

```vbnet
Imports GrapeCity.Win.MultiRow
Imports InputManCell = GrapeCity.Win.MultiRow.InputMan

Dim GcCharMaskCell1 As New InputManCell.GcCharMaskCell
GcCharMaskCell1.Name = "GcCharMaskCell1"
GcCharMaskCell1.Format = "AB"

GcMultiRow1.Template = Template.CreateGridTemplate(New Cell() {GcCharMaskCell1})
```

次の例では、半角大文字のアルファベットと数字（0～9）が入力可能になります。キーワード"X"で指定した16進数は、別のキーワードの"A"と"9"に含まれているので、無視されます。

```csharp
gcCharMaskCell1.Format = "AX9";
```

```vbnet
GcCharMaskCell1.Format = "AX9"
```

下のコードでは、すべての半角文字の入力が許可されます。キーワード"AaK9"で指定した文字種は"H"に包含されているので、この部分は無視されます。

```csharp
gcCharMaskCell1.Format = "AaK9H";
```

```vbnet
GcCharMaskCell1.Format = "AaK9H"
```

次に示す２つの例は、どちらもスペースを含むすべての文字種を許可するものです。デフォルトでは、最初の例のように設定されていますので、２つ目の例のようにキーワード"ＺH"を指定しなくても同じ動作となります。

```csharp
gcCharMaskCell1.Format = "";
gcCharMaskCell1.AllowSpace = GrapeCity.Win.Editors.AllowSpace.Both;

gcCharMaskCell1.Format = "ＺH";
gcCharMaskCell1.AllowSpace = GrapeCity.Win.Editors.AllowSpace.Both;
```

```vbnet
GcCharMaskCell1.Format = ""
GcCharMaskCell1.AllowSpace = GrapeCity.Win.Editors.AllowSpace.Both

GcCharMaskCell1.Format = "ＺH"
GcCharMaskCell1.AllowSpace = GrapeCity.Win.Editors.AllowSpace.Both
```

以下の２つのコードは、すべての文字種の入力を拒否します。スペースの入力も許可されません。この例が示すように、キーワード"^"は、その後に記述されたキーワードの補集合を表します。

```csharp
gcCharMaskCell1.Format = "^";
gcCharMaskCell1.AllowSpace = GrapeCity.Win.Editors.AllowSpace.None;

gcCharMaskCell1.Format = "^ＺH";
gcCharMaskCell1.AllowSpace = GrapeCity.Win.Editors.AllowSpace.None;
```

```vbnet
GcCharMaskCell1.Format = "^"
GcCharMaskCell1.AllowSpace = GrapeCity.Win.Editors.AllowSpace.None

GcCharMaskCell1.Format = "^ＺH"
GcCharMaskCell1.AllowSpace = GrapeCity.Win.Editors.AllowSpace.None
```

また、入力可能な文字種から特定の文字種を除外することもできます。次のコードはすべての全角文字から絵記号だけを除外します。

```csharp
gcCharMaskCell1.Format = "Ｚ^Ｅ";
```

```vbnet
GcCharMaskCell1.Format = "Ｚ^Ｅ"
```

特定の文字を書式に設定することも可能です。記号から「^、@、\\、$」の4文字を除外するには以下のように記述します。

```csharp
gcCharMaskCell1.Format = "@^\\^\\@\\\\$";
```

```vbnet
GcCharMaskCell1.Format = "@^\^\@\\$"
```

## 文字列の自動変換

[AutoConvert](gcdocsite__documentlink?toc-item-id=43b6442d-9208-468f-a6ec-a661a4de1f1f)プロパティをTrueに設定すると、Formatプロパティの設定内容に基づいて、変換可能な文字はすべて自動的に変換されます。たとえば、Formatプロパティで"A"キーワードが設定されていると、小文字を入力しても自動的に大文字に変換されます。また、全角文字だけが許可されている場合は、入力された半角文字は全角文字に変換されます。
セル内部で行われる自動変換の手順を以下に示します。

1. 小文字から大文字、または大文字から小文字への変換を行います。
2. 手順１の変換が行われない場合、全角から半角、または半角から全角への変換を行います。
3. 手順２の変換が行われない場合、全角大文字から半角小文字、全角小文字から半角大文字、半角大文字から全角小文字、半角小文字から全角大文字のいずれかの変換を行います。

半角カタカナ、全角カタカナ、およびひらがなは、次のように変換されます。

* 半角カタカナは全角カタカナに変換。変換できない場合はひらがなに変換。
* 全角カタカナは半角カタカナに変換。変換できない場合はひらがなに変換。
* ひらがなは全角カタカナに変換。変換できない場合は半角カタカナに変換。

## スペース入力の制御

[AllowSpace](gcdocsite__documentlink?toc-item-id=bc5f322a-a824-4d8e-aaa1-5cdaabc099e4)プロパティは、Formatの設定に依存せずに入力可能なスペースの種類を設定します。AllowSpaceプロパティが[AllowSpace.Wide](gcdocsite__documentlink?toc-item-id=f22b8f77-9012-40c7-9ea3-f51786cc620c)に設定されている場合、Formatプロパティにキーワード"H"のみが設定されていても、セルには全角のスペースのみ入力可能です。また、同様にAllowSpaceプロパティが[AllowSpace.Narrow](gcdocsite__documentlink?toc-item-id=f22b8f77-9012-40c7-9ea3-f51786cc620c)に設定されている場合、キーワード"Ｚ"のみが設定されていても、半角のスペースだけが入力可能になります。

| AllowSpaceの値 | 説明 |
| ------------ | --- |
| Both | 半角、全角の両方のスペースが入力可能 |
| Narrow | 半角のスペースのみ入力可能 |
| Wide | 全角のスペースのみ入力可能 |
| None | スペースの入力はできません |

> !type=warning
> 既存のテキストにスペースが含まれているときに、AllowSpaceを[AllowSpace.None](gcdocsite__documentlink?toc-item-id=f22b8f77-9012-40c7-9ea3-f51786cc620c)に設定すると、それらのスペースがすべて削除されるので注意が必要です。

## 関連トピック

[GcCharMaskCell](gcdocsite__documentlink?toc-item-id=6213468d-8383-4747-9da7-55c8cdc02946)
[入力の制御](gcdocsite__documentlink?toc-item-id=911cdfa4-0d67-44bc-9134-fc41b1d56b58)
[マス目の設定](gcdocsite__documentlink?toc-item-id=67882c89-6124-435d-a8b3-cd5bfe95796f)
[視覚的な補助](gcdocsite__documentlink?toc-item-id=ad3eae02-d613-45bd-93ed-18e46c0bbcba)
[外観の設定](gcdocsite__documentlink?toc-item-id=8df94c76-b7d6-4897-ae89-73b5e0127018)
[データベース接続](gcdocsite__documentlink?toc-item-id=ee3d6383-1642-4d0c-963e-f01192324109)