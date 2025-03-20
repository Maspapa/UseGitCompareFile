GcDateTimeCellの主要機能である書式フィールドの設定とその活用方法について解説します。

## 書式設定の概要

GcDateTimeCellの書式には、入力用と表示用の２つがあり、それぞれ入力フィールドと表示フィールドを使って書式を設定します。
入力フィールドを設定するには、[Fields](gcdocsite__documentlink?toc-item-id=440e0161-07b6-4018-b351-e2ec0f335ae3)プロパティが参照する[DateTimeFieldCollection](gcdocsite__documentlink?toc-item-id=def2bbd2-a165-4f12-a721-e74eb3018c61)クラスを使用します。DateTimeFieldCollectionは、セル内の各フィールドを表す[DateField](gcdocsite__documentlink?toc-item-id=7bcc86c5-8962-4081-8b56-4c937604d35d)のコレクションを保持するクラスです。
一方、表示フィールドを設定するには、[DisplayFields](gcdocsite__documentlink?toc-item-id=fdd65429-f1cc-412f-ad4d-acc196b9b69b)プロパティが参照する[DateTimeDisplayFieldCollection](gcdocsite__documentlink?toc-item-id=81fd8676-8105-45a1-9fb2-ef7ef5503bd7)を使用します。DateTimeDisplayFieldCollectionは、セル内の各フィールドを表す[DateDisplayField](gcdocsite__documentlink?toc-item-id=66a92189-91fb-441a-86dd-6a441a568761)のコレクションを保持するクラスです。
GcDateTimeCellの書式を設定するには、それぞれのコレクションの[Add](gcdocsite__documentlink?toc-item-id=0f0fd190-756c-41f7-bff3-7cfbb6a8bd7d)メソッドもしくは[AddRange](gcdocsite__documentlink?toc-item-id=03c7c770-d785-447f-bc30-94e61de916fa)メソッドを使用して直接フィールドオブジェクトを追加する方法と、AddRangeメソッドのオーバーライドの１つを使用して、キーワード文字列によりフィールドを自動生成する方法があります。それぞれの方法による書式の設定方法については、以下のトピックを参照してください。

* [フィールドオブジェクトによる書式設定](gcdocsite__documentlink?toc-item-id=5f218ebc-6bf1-4c1b-a58b-4c253539cdc3)
* [キーワードによる書式設定](gcdocsite__documentlink?toc-item-id=4c7b252a-ffb8-4719-9086-6d041e558f0d)

## リテラル文字とプロンプト文字

[ShowLiterals](gcdocsite__documentlink?toc-item-id=adc60d59-717b-4f9e-85aa-e761550335e2)プロパティを使えば、入力中にリテラル文字列を表示するかどうかを指定できます。
リテラル文字とは、[DateLiteralField](gcdocsite__documentlink?toc-item-id=e4243ec4-11f5-4c6b-8690-1666353f6f51)（リテラルフィールド）で定義された文字列をそのまま表示する文字列をいいます。
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/04gcdatetime/datetime_literal.png)
また、リテラルフィールド以外のフィールドには、プロンプト文字を設定することができます。プロンプト文字を使用することで、入力フィールドを明示的に表示したり入力文字数を視覚的に表すことができます。 プロンプト文字はセルの[PromptChar](gcdocsite__documentlink?toc-item-id=381b8fac-3e0e-4e3f-96f2-205ffdf73fdc)プロパティを使用して設定できます。なお、各フィールドのPromptCharプロパティを設定するとフィールドごとに異なるプロンプト文字も設定できます。
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/04gcdatetime/gcdatetime_prompt.png)
（図）プロンプト文字（"\_"）
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/imimages/04gcdatetime/gcdatetime_partprompt.png)
（図）月と分フィールドのみ異なるプロンプト文字（"\*")

## 自由書式入力

InputManCellでサポートされません。

## フィールド操作

[DefaultActiveField](gcdocsite__documentlink?toc-item-id=00b0249c-565d-4fcd-830b-e85f8a028634)プロパティを使用すると、セルがフォーカスを受け取ったときにキャレットを配置するフィールドを指定できます。現在キャレットが置かれているフィールドは、GcDateTimeEditingControl.ActiveFieldプロパティで取得できます。
フィールドコレクション内の特定のフィールドにアクセスする場合、次のいずれかの方法を使うことができます。

* インデックスからフィールドにアクセス
* キー（文字列）からフィールドにアクセス

コレクションのインデックスがわかっている場合は、インデックスを使ってフィールドを取得することができます。
次のサンプルはインデックスを使ってフィールドを取得する例です。ここでは GcDateTimeCell の3番目のフィールドを取得する例です。

```csharp
GrapeCity.Win.MultiRow.InputMan.GcDateTimeCell cell = (GrapeCity.Win.MultiRow.InputMan.GcDateTimeCell)gcMultiRow1.Rows[0].Cells[0];
GrapeCity.Win.MultiRow.InputMan.DateField myField = cell.Fields[2];
```

```vbnet
Dim cell As GrapeCity.Win.MultiRow.InputMan.GcDateTimeCell = DirectCast(GcMultiRow1.Rows(0).Cells(0), GrapeCity.Win.MultiRow.InputMan.GcDateTimeCell)
Dim MyField As GrapeCity.Win.MultiRow.InputMan.DateField = cell.Fields(2)
```

また、インデックスを使わず、設定したキー（文字列）を使って特定のフィールドにアクセスすることもできます。
キーは、各フィールドの[Name](gcdocsite__documentlink?toc-item-id=3f1c981e-c415-46d7-b3d6-c117d3ef9b28)プロパティにキーとして文字列を設定します。
次のサンプルはキーを使ってフィールドを取得する例です。ここでは GcDateTimeCell の特定のフィールドのName プロパティに予め"Key1"という文字列が設定されていることを前提にしています。

```csharp
GrapeCity.Win.MultiRow.InputMan.DateField myField = (gcMultiRow1.CurrentCell as GrapeCity.Win.MultiRow.InputMan.GcDateTimeCell).Fields["Key1"];
```

```vbnet
Dim MyField As GrapeCity.Win.MultiRow.InputMan.DateField = DirectCast(GcMultiRow1.CurrentCell, GrapeCity.Win.MultiRow.InputMan.GcDateTimeCell).Fields("Key1")
```

## イベントの利用

フィールド間のキャレットの移動を検出するには、GcDateTimeEditingControlのフィールド間のキャレットの移動によって発生する次の２つのイベントが使用します。

* FieldEnterイベント（編集コントロール内でフィールドがアクティブになったときに発生します。）
* FieldLeaveイベント（編集コントロール内でフィールドがアクティブでなくなったときに発生します。）

これらのイベントを使えば、フィールド毎に入力された値をチェックすることや、その値に応じた独自処理の実装など、フィールドを使った細やかな処理の実装を可能になります。

## 関連トピック

[GcDateTimeCell](gcdocsite__documentlink?toc-item-id=b80001db-fab9-48f7-baab-a639554c60a2)
[入力の制御](gcdocsite__documentlink?toc-item-id=6564107e-1f0b-4a35-bd8e-059b15c79f37)
[視覚的な補助](gcdocsite__documentlink?toc-item-id=9d947385-bd2c-4754-beba-489cbdd8b536)
[サイドボタンの設定](gcdocsite__documentlink?toc-item-id=a530eeec-b4e0-4bae-96bf-36a3c1226cd5)
[ドロップダウンカレンダー](gcdocsite__documentlink?toc-item-id=636ed515-d9bd-4cd4-95e1-a248269ffe78)
[ドロップダウン日付時刻ピッカー](gcdocsite__documentlink?toc-item-id=bba04be6-e380-412d-8f5d-f5fa1d59e4f0)
[外観の設定](gcdocsite__documentlink?toc-item-id=d2ac536f-45ed-4239-b020-0a46fa9baa14)
[和暦表示の設定](gcdocsite__documentlink?toc-item-id=346274df-ba85-4704-94de-81503622da40)
[データベース接続](gcdocsite__documentlink?toc-item-id=88836a36-6f2a-4e07-9825-e71e0993bf66)