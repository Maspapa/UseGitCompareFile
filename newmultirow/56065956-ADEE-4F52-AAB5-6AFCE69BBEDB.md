ComboBoxCellでComboBox.SelectedIndexChangedイベントと同様の処理を行うには、GcMultiRow.CellEditedFormattedValueChangedイベントによる実装と、ComboBoxEditingControl.SelectedIndexChangedイベントによる実装の２種類の方法があります。
通常はGcMultiRow.CellEditedFormattedValueChangedイベントによる実装が推奨されます。

## GcMultiRow.CellEditedFormattedValueChangedイベントによる実装

```csharp
using GrapeCity.Win.MultiRow;

private void gcMultiRow1_CellEditedFormattedValueChanged(object sender, GrapeCity.Win.MultiRow.CellEditedFormattedValueChangedEventArgs e)
{
    GcMultiRow gcMultiRow = sender as GcMultiRow;
    Cell currentCell = gcMultiRow.Rows[e.RowIndex].Cells[e.CellIndex];

    if (currentCell is ComboBoxCell)
    {
        Console.WriteLine("{0},{1}", e.Reason.ToString(), currentCell.EditedFormattedValue);
    }
}
```

```vbnet
Imports GrapeCity.Win.MultiRow

Private Sub GcMultiRow1_CellEditedFormattedValueChanged(ByVal sender As System.Object, ByVal e As GrapeCity.Win.MultiRow.CellEditedFormattedValueChangedEventArgs) Handles GcMultiRow1.CellEditedFormattedValueChanged
    Dim gcMultiRow As GcMultiRow = TryCast(sender, GcMultiRow)
    Dim currentCell As Cell = gcMultiRow.Rows(e.RowIndex).Cells(e.CellIndex)

    If TypeOf currentCell Is ComboBoxCell Then
        Console.WriteLine("{0},{1}", e.Reason.ToString(), currentCell.EditedFormattedValue)
    End If
End Sub
```

## ComboBoxEditingControl.SelectedIndexChangedイベントによる実装

5.0Jと同じように、ComboBoxEditingControl.SelectedIndexChangedイベントを使う場合、セルの初期化時のイベント検出を避けるため、TextBoxEditingControlTextChangedイベントとは異なる実装方法を使用する必要があります。
```csharp
using GrapeCity.Win.MultiRow;

private ComboBoxEditingControl _comboBoxEditingControl1 = null;

private void Form1_Load(object sender, System.EventArgs e)
{
    ComboBoxCell comboBoxCell1 = new ComboBoxCell();
    comboBoxCell1.Name = "comboBoxCell1";
    comboBoxCell1.Items.AddRange("A", "B", "C");
    LabelCell labelCell1 = new LabelCell();
    labelCell1.Name = "labelCell1";
    LabelCell labelCell2 = new LabelCell();
    labelCell2.Name = "labelCell2";

    GcMultiRow1.Template = Template.CreateGridTemplate(new Cell[] {comboBoxCell1, labelCell1, labelCell2});
}

private void gcMultiRow1_EditingControlShowing(object sender, GrapeCity.Win.MultiRow.EditingControlShowingEventArgs e)
{
    // セル編集コントロールのイベントを追加する
    if (e.Control is ComboBoxEditingControl)
    {
        this._comboBoxEditingControl1 = e.Control as ComboBoxEditingControl;
        this._comboBoxEditingControl1.SelectedIndexChanged += new EventHandler(_comboBoxEditingControl1_SelectedIndexChanged);
    }
}

// セル編集コントロールのイベント(ComboBox.SelectedIndexChangedと同じ)
private void _comboBoxEditingControl1_SelectedIndexChanged(object sender, EventArgs e)
{
    ComboBoxEditingControl comboBox = sender as ComboBoxEditingControl;
    comboBox.GcMultiRow.CurrentRow.Cells["labelCell1"].Value = comboBox.Items[comboBox.SelectedIndex].ToString();
    comboBox.GcMultiRow.CurrentRow.Cells["labelCell2"].Value = comboBox.SelectedIndex;
}

private void gcMultiRow1_CellEndEdit(object sender, GrapeCity.Win.MultiRow.CellEndEditEventArgs e)
{
    // セル編集コントロールのイベントを削除する
    if (this._comboBoxEditingControl1 != null)
    {
        this._comboBoxEditingControl1.SelectedIndexChanged -= new EventHandler(_comboBoxEditingControl1_SelectedIndexChanged);
        this._comboBoxEditingControl1 = null;
    }
}
```

```vbnet
Imports GrapeCity.Win.MultiRow

Private _comboBoxEditingControl1 As ComboBoxEditingControl = Nothing

Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load
    Dim ComboBoxCell1 As New ComboBoxCell()
    ComboBoxCell1.Name = "ComboBoxCell1"
    ComboBoxCell1.Items.AddRange("A", "B", "C")
    Dim LabelCell1 As New LabelCell()
    LabelCell1.Name = "LabelCell1"
    Dim LabelCell2 As New LabelCell()
    LabelCell2.Name = "LabelCell2"

    GcMultiRow1.Template = Template.CreateGridTemplate(New Cell() {ComboBoxCell1, LabelCell1, LabelCell2})
End Sub

Private Sub GcMultiRow1_EditingControlShowing(ByVal sender As System.Object, ByVal e As GrapeCity.Win.MultiRow.EditingControlShowingEventArgs) Handles GcMultiRow1.EditingControlShowing
    ' セル編集コントロールのイベントを追加する
    If TypeOf e.Control Is ComboBoxEditingControl Then
        Me._comboBoxEditingControl1 = TryCast(e.Control, ComboBoxEditingControl)
        AddHandler Me._comboBoxEditingControl1.SelectedIndexChanged, AddressOf Me._comboBoxEditingControl1_SelectedIndexChanged
    End If
End Sub

' セル編集コントロールのイベント(ComboBox.SelectedIndexChangedと同じ)
Private Sub _comboBoxEditingControl1_SelectedIndexChanged(ByVal sender As System.Object, ByVal e As System.EventArgs)
    Dim comboBox As ComboBoxEditingControl = TryCast(sender, ComboBoxEditingControl)
    comboBox.GcMultiRow.CurrentRow.Cells("LabelCell1").Value = comboBox.Items(comboBox.SelectedIndex).ToString()
    comboBox.GcMultiRow.CurrentRow.Cells("LabelCell2").Value = comboBox.SelectedIndex
End Sub

Private Sub GcMultiRow1_CellEndEdit(ByVal sender As System.Object, ByVal e As GrapeCity.Win.MultiRow.CellEndEditEventArgs) Handles GcMultiRow1.CellEndEdit
    ' セル編集コントロールのイベントを削除する
    If Me._comboBoxEditingControl1 Is Nothing Then
        RemoveHandler Me._comboBoxEditingControl1.SelectedIndexChanged, AddressOf Me._comboBoxEditingControl1_SelectedIndexChanged
        Me._comboBoxEditingControl1 = Nothing
    End If
End Sub
```

## 関連トピック

[コンボボックス型セル（ComboBoxCell）](gcdocsite__documentlink?toc-item-id=b3db033b-8448-45cf-8763-aee7e36f797e)
[選択項目のインデックス取得](gcdocsite__documentlink?toc-item-id=8e8701f6-7f0d-48b0-bae5-d119b6ef78eb)