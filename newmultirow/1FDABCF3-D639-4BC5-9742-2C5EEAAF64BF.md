
GcCalendarCellのヘッダに表示できる書式の設定について解説します。

## 月-日カレンダーの書式設定

[CalendarType](gcdocsite__documentlink?toc-item-id=323b3f79-76b2-4628-9a76-38eb8833071c)プロパティが[CalendarType.MonthDay](gcdocsite__documentlink?toc-item-id=31964b54-7d28-4b2d-b3c1-bf9a0d74ee4a)のとき（月-日カレンダー）のヘッダの表示書式は[HeaderFormat](gcdocsite__documentlink?toc-item-id=323b3f79-76b2-4628-9a76-38eb8833071c)プロパティで設定します。HeaderFormatプロパティに以下のキーワードとリテラル文字を設定することで、書式を作成します。

| キーワード | 説明 |
| --- | --- |
| g | 年号の頭文字をアルファベットで表示（M、T、S、H、R） |
| gg | 年号の頭文字を漢字で表示（明、大、昭、平、令） |
| ggg | 年号の正式名称を漢字で表示（明治、大正、昭和、平成、令和） |
| e | 和暦年を２桁で表示（先頭に0を付けない） |
| ee | 和暦年を２桁で表示（先頭に0を付ける） |
| E | 和暦年を２桁で表示し開始年を元と表示（先頭に0を付けない）<br />（例：平成元年）<br /> |
| EE | 和暦年を２桁で表示し開始年を元と表示（先頭に0を付ける）<br />（例：平成元年）<br /> |
| y | 年を２桁で表示（先頭に0を付けない） |
| yy | 年を２桁で表示（先頭に0を付ける） |
| yyy | 年を４桁で表示（先頭に0を付けない） |
| yyyy | 年を４桁で表示（先頭に0を付ける） |
| M | 月を２桁の数字で表示（先頭に0を付けない） |
| MM | 月を２桁の数字で表示（先頭に0を付ける） |
| MMM | 月を省略形で表示<br />（DateTimeFormatInfo.AbbreviatedMonthNames() で指定された形式）<br /> |
| MMMM | 月を正式名称で表示<br />（DateTimeFormatInfo.MonthNames()で指定された形式）<br /> |
| \\（Chr(92)） | キーワードをリテラル文字として表示 |

<br />


> !type=warning
>
> *   キーワード"e"、"ee"、"E"、または"EE"を使用する場合は、元号を表すキーワード"g"、"gg"、または"ggg"を必ず併用してください。
> *   和暦表示が可能な日付の範囲は、1868年9月1日～2087年12月31日です。この範囲を超えた場合は、西暦で表示されます。

次のサンプルコードはヘッダの書式を設定する例です。

```csharp
gcCalendarCell1.ShowHeader = true;
gcCalendarCell1.HeaderHeight = 25;
gcCalendarCell1.HeaderFormat = "ggg e年 M月";
```

```vbnet
GcCalendarCell1.ShowHeader = True
GcCalendarCell1.HeaderHeight = 25
GcCalendarCell1.HeaderFormat = "ggg e年 M月"
```

<br />

## 年-月カレンダーの書式設定

[CalendarType](gcdocsite__documentlink?toc-item-id=323b3f79-76b2-4628-9a76-38eb8833071c)プロパティが[CalendarType.YearMonth](gcdocsite__documentlink?toc-item-id=31964b54-7d28-4b2d-b3c1-bf9a0d74ee4a)（年-月カレンダー）のときの書式設定には、[YearMonthFormat](gcdocsite__documentlink?toc-item-id=323b3f79-76b2-4628-9a76-38eb8833071c)プロパティが参照する[YearMonthFormat](gcdocsite__documentlink?toc-item-id=82684e99-7889-43fa-bf05-b106cbae5adb)オブジェクトを使用します。

YearMonthFormatオブジェクトの[MonthFormat](gcdocsite__documentlink?toc-item-id=9eafd5a9-d9ee-43a2-954b-d516cede3c66)および[YearFormat](gcdocsite__documentlink?toc-item-id=d76d8878-21d9-49a4-8294-f52d59442d83)プロパティにキーワードとリテラル文字を設定することで、月の書式、年の書式をそれぞれ作成します。

#### 月の設定に関するキーワード

| キーワード | 説明 |
| --- | --- |
| M | 月を２桁の数字で表示（先頭に0を付けない） |
| MM | 月を２桁の数字で表示（先頭に0を付ける） |
| MMM | 月を省略形で表示<br />（DateTimeFormatInfo.AbbreviatedMonthNames() で指定された形式）<br /> |
| MMMM | 月を正式名称で表示<br />（DateTimeFormatInfo.MonthNames()で指定された形式）<br /> |

#### 年の設定に関するキーワード

| キーワード | 説明 |
| --- | --- |
| g | 年号の頭文字をアルファベットで表示（M、T、S、H、R） |
| gg | 年号の頭文字を漢字で表示（明、大、昭、平、令） |
| ggg | 年号の正式名称を漢字で表示（明治、大正、昭和、平成、令和） |
| e | 和暦年を２桁で表示（先頭に0を付けない） |
| ee | 和暦年を２桁で表示（先頭に0を付ける） |
| E | 和暦年を２桁で表示し開始年を元と表示（先頭に0を付けない）<br />（例：平成元年）<br /> |
| EE | 和暦年を２桁で表示し開始年を元と表示（先頭に0を付ける）<br />（例：平成元年）<br /> |
| y | 年を２桁で表示（先頭に0を付けない） |
| yy | 年を２桁で表示（先頭に0を付ける） |
| yyy | 年を４桁で表示（先頭に0を付けない） |
| yyyy | 年を４桁で表示（先頭に0を付ける） |


> !type=warning
>
> *   キーワード"e"、"ee"、"E"、または"EE"を使用する場合は、元号を表すキーワード"g"、"gg"、または"ggg"を必ず併用してください。
> *   和暦表示が可能な日付の範囲は、1868年9月1日～2087年12月31日です。この範囲を超えた場合は、西暦で表示されます。

次のサンプルコードは、年-月カレンダーの表示書式を設定する方法を示します。

```csharp
gcCalendarCell1.CalendarType = GrapeCity.Win.Calendar.CalendarType.YearMonth;
gcCalendarCell1.YearMonthFormat.YearFormat = "ggg e年";
gcCalendarCell1.YearMonthFormat.MonthFormat = "MM月";
```

```vbnet
GcCalendarCell1.CalendarType = GrapeCity.Win.Calendar.CalendarType.YearMonth
GcCalendarCell1.YearMonthFormat.YearFormat = "ggg e年"
GcCalendarCell1.YearMonthFormat.MonthFormat = "MM月"
```

## 関連トピック

[GcCalendarCell](gcdocsite__documentlink?toc-item-id=5c66b65d-4c55-4789-8a07-8e32216ca253)

[レイアウトの変更](gcdocsite__documentlink?toc-item-id=ec9a15e1-311b-4a1c-972d-2b1eabd65071)

[カレンダーの操作](gcdocsite__documentlink?toc-item-id=36f73f20-19a2-4571-9dcb-591e1ee1e837)

[キーボードからの操作](gcdocsite__documentlink?toc-item-id=e70e569d-bed2-4b51-b0ec-b437f82912b3)

[スタイルの設定](gcdocsite__documentlink?toc-item-id=6a94c6aa-81e3-41bc-a45a-09aff2ba497d)

[休日の設定](gcdocsite__documentlink?toc-item-id=9f75582f-079b-4e5a-a0c8-8daf097f923f)

[休業日の設定](gcdocsite__documentlink?toc-item-id=93fe3668-cc67-4b54-b42a-6515be44c158)

[日付の選択と取得](gcdocsite__documentlink?toc-item-id=aec3550b-c240-4c73-ad30-2553bc0a2507)

[データベースへの接続](gcdocsite__documentlink?toc-item-id=af4ba527-0df7-42a3-b1f5-037ed5794607)

[祝日定義ファイルのインポート／エクスポート](gcdocsite__documentlink?toc-item-id=17ac25c3-6e23-4b97-9e71-6f357056feae)

[iCalendarファイルのインポート／エクスポート](gcdocsite__documentlink?toc-item-id=5fb8054d-bcf8-40e9-834c-3de9507cb4d5)

[カレンダーの手動描画](gcdocsite__documentlink?toc-item-id=0a830c95-ffd4-47ae-8ac3-20385e029647)

[日付のメモ設定](gcdocsite__documentlink?toc-item-id=bcc64849-d39e-43d1-9a4b-ed57c6e6e911)