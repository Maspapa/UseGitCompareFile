[GcComboFrame](gcdocsite__documentlink?toc-item-id=777d5900-dd11-4321-bd94-25b03f66f269)コントロールのサイドボタンの追加方法について、以下に解説します。

## サイドボタンの追加

サイドボタンは、GcComboFrameコントロールの左側か右側に表示するボタンで、ドロップダウンウィンドウを表示するほか、さまざまな機能を実装することができます。デフォルトでは、ひとつの DropDownButton が表示されます。アプリケーションのニーズに合わせて追加・カスタマイズすることが可能です。
サイドボタンを編集するには、次のいずれの方法で「サイドボタン コレクション エディタ」を開いて行います。

* GcComboFrame コントロールを選択して、スマートタグを開き、「サイドボタンの編集...」を選択します。
<br>
    ![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gccomboframe.sidebutton_smarttag.png)
<br>
* GcComboFrame コントロールを選択して、プロパティウィンドウで SideButtons プロパティの右側に表示されるボタンをクリックします。
<br>
    ![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gccomboframe.sidebutton_ppw.png)
<br>

＜サイドボタン コレクション エディタ＞
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gccomboframe.sidebuttoncollectioneditor1.png)

「サイドボタン コレクション エディタ」で下記のサイドボタンを任意に追加し、それぞれのプロパティを設定することができます。また、矢印ボタンを使ってボタンを表示する順番を設定できます。

#### 使用可能なサイドボタン

GcComboFrameコントロールでは、下記の種類のサイドボタンを使用できます。これらの詳細については、各クラスのトピックを参照してください。

| 名前 | 説明 |
| --- | --- |
| [ColorPickerButton](gcdocsite__documentlink?toc-item-id=b0916441-9e0a-43eb-9848-e06a03fcd6aa) | コントロールで使用する色を採取する機能を提供します。 |
| [DropDownButton](gcdocsite__documentlink?toc-item-id=4022f724-4741-436d-bbce-2e0a10c49b70) | ドロップダウンウィンドウを開く機能を提供します。 |
| [SideButton](gcdocsite__documentlink?toc-item-id=7dbfc489-7e76-4a21-baad-6214aef334fb) | 標準のボタン機能を提供します。 |
| [SpinButton](gcdocsite__documentlink?toc-item-id=f0f8b295-43a7-45f3-8b3f-7ff6fcb24bd4) | コントロールの値をスピンアップまたはスピンダウンする機能を提供します。 |
| [SymbolButton](gcdocsite__documentlink?toc-item-id=5df2f876-1d0d-4c51-9ae6-4ba5189df6d4) | 記号付きのボタン機能を提供します。 |

設計時に、コントロールに追加されているサイドボタンをクリックすることで、該当するボタンが選択状態となり、プロパティウィンドウでプロパティを設定することができます。
各サイドボタンは Position プロパティをもちます。このプロパティを設定することで、該当するボタンをコントロールの境界線の左内側、左外側、右内側、あるいは右外側のいずれに配置するかを指定することができます。
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gccomboframe.sidebutton_position.png)

#### ColorPickerButtonの活用例

この例では、ColorPickerButton を使って文字色を変更する方法を示します。コンテントパネルにテキストボックス（TextBox1）が配置されていることを前提とします。

1. 前述のようにサイドボタンコレクションエディタを使用して、GcComboFrame コントロールに ColorPickerButton を追加します。
2. ColorPickerButton の PickingColor イベントに下記のコードを記述します。

    ```csharp
    private void colorPickerButton1_PickingColor(object sender, GrapeCity.Win.Common.PickingColorEventArgs e)
    {
        textBox1.ForeColor = e.Color; 
    }
    ```

    ```vbnet
    Private Sub ColorPickerButton1_PickingColor(ByVal sender As System.Object, ByVal e As GrapeCity.Win.Common.PickingColorEventArgs) Handles ColorPickerButton1.PickingColor
        TextBox1.ForeColor = e.Color
    End Sub
    ```

<br>
    上記により、ColorPickerButton をマウスで押下して画面の任意の色に移動すると、移動先の色がテキストの文字色に設定されます。
<br>
    ![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gccomboframe.sample_colorpickerbutton.png)

#### SymbolButtonの活用例

この例では、[SymbolButton](gcdocsite__documentlink?toc-item-id=5df2f876-1d0d-4c51-9ae6-4ba5189df6d4)を使って日付を週単位で遷移させる方法を示します。コンテントパネルに日付コントロール（DateTimePicker1）を配置していることを前提とします。

1. 前述の方法で、GcComboFrame コントロールに SymbolButton を２つ追加します。
2. 追加した SymbolButton のプロパティを下記のように設定します。

    | @cols=2:SymbolButton1 |
    | ------------- | ------------- |
    | Symbol | DoubleArrow |
    | SymbolDirection | Left |
    | @cols=2:@rows=1:SymbolButton2 |
    | Symbol | DoubleArrow |
    | SymbolDirection | Right |
3. それぞれの SymbolButton のClick イベントに下記のコードを記述します。

    ```csharp
    private void symbolButton1_Click(object sender, EventArgs e)
    {
        dateTimePicker1.Value = dateTimePicker1.Value.AddDays(-7);
    }
    
    private void symbolButton2_Click(object sender, EventArgs e)
    {
        dateTimePicker1.Value = dateTimePicker1.Value.AddDays(7);
    }
    ```

    ```vbnet
    Private Sub SymbolButton1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SymbolButton1.Click
        DateTimePicker1.Value = DateTimePicker1.Value.AddDays(-7)
    End Sub
    
    Private Sub SymbolButton2_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SymbolButton2.Click
        DateTimePicker1.Value = DateTimePicker1.Value.AddDays(7)
    End Sub
    ```

<br>
    上記により、SymbolButton をクリックするたびに日付が一週間単位に遷移します。
<br>
    ![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gccomboframe.sample_symbolbutton1.png) ![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gccomboframe.sample_symbolbutton2.png)

#### サイドボタンへのスピン動作の割り当て

[SideButton](gcdocsite__documentlink?toc-item-id=7dbfc489-7e76-4a21-baad-6214aef334fb)クラスはスピン動作の割り当てを設定する Behavior プロパティを提供しますが、GcComboFrame コントロールでは既定のスピン動作が存在しないため、設定値に関わらず無効です。

#### シンボルボタンへのスピン動作の割り当て

SymbolButton クラスはスピン動作の割り当てを設定する Behavior プロパティを提供しますが、GcComboFrame コントロールでは既定のスピン動作が存在しないため、設定値に関わらず無効です。

## 関連トピック

[GcComboFrameコントロール](gcdocsite__documentlink?toc-item-id=46b2c5fc-42b5-412a-8fc6-3abb9fac0188)
[コンテントパネルの設定](gcdocsite__documentlink?toc-item-id=650c1f9b-78a4-4a3c-8ca5-207dfeaaf193)
[ドロップダウンウィンドウの設定](gcdocsite__documentlink?toc-item-id=7b31f358-810b-4293-8948-ed9b950fac7f)
[機能の実装](gcdocsite__documentlink?toc-item-id=c914cbda-3c37-493e-b6ec-67ebfa774a1b)
[タッチ機能](gcdocsite__documentlink?toc-item-id=2c681b8c-0b9d-43fc-89dc-d1235205cb48)