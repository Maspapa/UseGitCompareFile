GcMultiRowコントロールでは、ドラッグ＆ドロップで行を移動することができます。
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/userguide/rowcell_moverow_01.png)

> !type=warning
>
> * 行ヘッダ型セルをドラッグ＆ドロップした場合に行の移動が行われます。
> * 行ヘッダ型セル以外のセル型をドラッグ＆ドロップした場合、行の移動は行われずにセルの選択操作になります。

## 行移動の設定

ドラッグ＆ドロップで移動できる行は、「1行のみ」または「複数行」を指定できます。
1行のみ移動できるようにするには、[AllowRowMove](gcdocsite__documentlink?toc-item-id=c59f0e22-4bfc-4c9a-862b-beac70960456)プロパティにTrueを設定します。

```csharp
gcMultiRow1.AllowRowMove = true;
```

```vbnet
GcMultiRow1.AllowRowMove = True
```

複数行の移動をする場合には、[AllowRowMoveMultiple](gcdocsite__documentlink?toc-item-id=e08694ab-9eb0-49f1-8c93-da4f9b80947f)プロパティにTrueを設定します。

> !type=warning
>
> * 複数行の移動を有効にするにはAllowRowMoveプロパティもTrueに設定されている必要があります。

```csharp
gcMultiRow1.AllowRowMove = true;
gcMultiRow1.AllowRowMoveMultiple = true;
```

```vbnet
GcMultiRow1.AllowRowMove = True
GcMultiRow1.AllowRowMoveMultiple = True
```

## 移動先を示す線色の設定

ドラッグ＆ドロップで行を移動する場合、移動先の行を示す線が表示されます。この線の色は[MoveRowLineColor](gcdocsite__documentlink?toc-item-id=7bc90f4d-6d3b-4d16-a2cd-c0713b846ace)プロパティで変更することができます。
次のコードは、移動先の行を示す線を緑色に設定します。

```csharp
gcMultiRow1.MoveRowLineColor = Color.Green;
```

```vbnet
GcMultiRow1.MoveRowLineColor = Color.Green;
```

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/userguide/rowcell_moverow_02.png)

## イベント処理

ドラッグ＆ドロップで行の移動が完了すると[RowDragMoveCompleted](gcdocsite__documentlink?toc-item-id=ee9fc38c-6aab-41f6-a436-5d529b16ab52)イベントが発生します。RowDragMoveCompletedイベントでは、移動先の行インデックスの取得や、行移動のキャンセルができます。
次のコードでは、10行目以降に行を移動した場合に行移動をキャンセルします。

```csharp
private void gcMultiRow1_RowDragMoveCompleted(object sender, GrapeCity.Win.MultiRow.DragMoveCompletedEventArgs e)
{
    if(e.ToIndex > 9)
    {
        // 行の移動をキャンセルします。
        e.Cancel = true;
    }
}
```

```vbnet
Private Sub GcMultiRow1_RowDragMoveCompleted(sender As Object, e As GrapeCity.Win.MultiRow.DragMoveCompletedEventArgs) Handles GcMultiRow1.RowDragMoveCompleted
    If e.ToIndex > 9 Then
        ' 行の移動をキャンセルします。
        e.Cancel = True
    End If
End Sub
```

## 関連トピック

[行とセル](gcdocsite__documentlink?toc-item-id=324fb6a9-dfd4-47c6-a50b-e5d6a733482c)
[現在の行](gcdocsite__documentlink?toc-item-id=7b0ccaf9-9a5f-4a5f-8213-ad223b742c47)
[現在のセル](gcdocsite__documentlink?toc-item-id=6a3e5e39-1e55-4d17-92f8-f98e089d50d6)
[行の追加](gcdocsite__documentlink?toc-item-id=6a5f283a-fdc8-42fa-af13-1298526d1974)
[行の削除](gcdocsite__documentlink?toc-item-id=722f1dee-d553-42d5-8c58-5f9c89e3edb3)
[行の固定](gcdocsite__documentlink?toc-item-id=6bd87f6c-4ec6-4996-ad1b-90a1ea751ff6)
[行数の設定と取得](gcdocsite__documentlink?toc-item-id=7f09d5fd-1715-4c72-bd9a-9d59f7302ae2)
[セル数の取得](gcdocsite__documentlink?toc-item-id=b2694627-470d-4dc7-8892-0e1a86a847b6)
[非スクロール領域](gcdocsite__documentlink?toc-item-id=9c2ffa5b-afc7-4e48-a7dd-8ea7ed014357)
[選択された行とセル](gcdocsite__documentlink?toc-item-id=34eab7a7-4714-49ae-b8df-7afa70750da1)
[セルの選択禁止](gcdocsite__documentlink?toc-item-id=44b1d9b5-a649-4d0d-b686-4884fcfd887a)
[セルの無効表示](gcdocsite__documentlink?toc-item-id=8fdf67b2-a648-40ce-b095-ca253fa79ad2)
[行とセルのスタイル](gcdocsite__documentlink?toc-item-id=35fe0c78-93bb-4048-8b2d-3e76d5c4a46d)
[表示と非表示](gcdocsite__documentlink?toc-item-id=740237fd-48df-4acb-bf6e-e927ba73941e)
[セルの編集](gcdocsite__documentlink?toc-item-id=9c3197b6-f2e2-4c66-9f4e-03d277a8c087)
[エラーメッセージの表示](gcdocsite__documentlink?toc-item-id=c7f2f4ef-e8a2-4cdb-90be-1a4e8ded871a)
[セルの読み取り専用](gcdocsite__documentlink?toc-item-id=3aed4939-b469-4405-a52a-e07d9aff2327)
[セルノート](gcdocsite__documentlink?toc-item-id=ecd20ea8-d990-4308-9bfc-e55491f0c3ee)