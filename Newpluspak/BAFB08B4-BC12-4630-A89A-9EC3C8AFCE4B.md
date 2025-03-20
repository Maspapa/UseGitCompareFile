バルーンチップのウィンドウの中にはコントロールを追加して独自のバルーンチップを作ることができます。ここでは、バルーンチップをカスタマイズする方法について解説します。

## 概要

バルーンチップにコントロールを追加するには、バルーンチップ内にコントロールを配置する必要があります。コントロールはバルーンチップ内の下図の位置に配置することができます。バルーンチップの大きさは追加されたコントロールのサイズによって自動的にサイズが調整されます。バルーンチップが表示可能なサイズの上限は[MaxWidth](gcdocsite__documentlink?toc-item-id=3ac7a6e6-aebf-42b0-aa75-ceea30b131ea)と[MaxHeight](gcdocsite__documentlink?toc-item-id=a9526805-24e4-495b-a33a-b3d0b0bfa912)プロパティで設定できます。デフォルトでは、幅（MaxWidth）は600ピクセルです。高さ（MaxHeight）には制限は設定されていません。貼り付けたコントロールのサイズが大きくバルーンチップ内に表示しきれない場合は、スクロールバーが表示されます。
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gcballoontip.balloontipcustomarea.png)

## コントロールの配置

バルーンチップ内にコントロールを配置するには、BalloonTipInformation オブジェクトの[CustomControl](gcdocsite__documentlink?toc-item-id=be359e7c-ed69-4a0d-8de8-2d627cc6a4e3) プロパティに配置するコントロールを設定します。例えば、テキストボックスコントロール（TextBox1）に設定されているバルーンチップにリンクラベル（LinkLabel1）を追加するには次のように行います。

```csharp
gcBalloonTip1.GetBalloonTipInformation(textBox1).CustomControl = linkLabel1;
```

```vbnet
GcBalloonTip1.GetBalloonTipInformation(TextBox1).CustomControl = LinkLabel1
```

バルーンチップ内に表示されるコントロールは (0, 0)の位置に配置されます。したがって、バルーンチップ内の意図した位置に表示するには、Panelやコンテナ（Container）コントロール等のコンテナにコントロールを配置してコンテナ上でLocation プロパティを設定し、そのコンテナをCustomControl プロパティに設定する必要があります。
また、CustomControl プロパティには、１つのコントロールしか設定できません。バルーンチップに複数のコントロール表示したい場合は、Panelやコンテナ（Container）コントロール等のコンテナに表示したいコントロールを貼り付け、コンテナを CustomControl プロパティに設定します。

## 活用例

ここでは、ボタンの Click イベントで、GcContainer コントロールを配置したバルーンチップを表示する例を紹介します。ここでは、ボタン（Button1）、コンテナコントロール（GcContainer1）とGcBalloonTip コンポーネント（GcBalloonTip1）がフォームに貼り付けられていることを前提にしています。

```csharp
using GrapeCity.Win.Components;

private void Form1_Load(object sender, System.EventArgs e)
{
    Label label1 = new Label();
    label1.Text = "問い合わせ先：";
    label1.Location = new Point(0, 0);
    label1.AutoSize = true;
    gcContainer1.Controls.Add(label1);

    Label label2 = new Label();
    label2.Text = "メシウス株式会社";
    label2.Location = new Point(20, 15);
    label2.AutoSize = true;
    gcContainer1.Controls.Add(label2);

    LinkLabel linkLabel1 = new LinkLabel();
    linkLabel1.Text = "https://developer.mescius.jp/";
    linkLabel1.Location = new Point(20, 30);
    linkLabel1.AutoSize = true;
    gcContainer1.Controls.Add(linkLabel1);

    // バルーンチップに追加するコンテナコントロールをフォームから削除します。 
    Controls.Remove(gcContainer1);

    // ボタンにバルーンチップを設定します。 
    BalloonTipInformation myTipInfo = new BalloonTipInformation();
    gcBalloonTip1.SetBalloonTipInformation(button1, myTipInfo);
    myTipInfo.Caption = "カスタムバルーンチップ";
    myTipInfo.Text = "バルーンチップにコンテナコントロールを追加";

    // コンテナをバルーンチップに配置します。 
    gcContainer1.Visible = true;
    myTipInfo.CustomControl = gcContainer1;
}

private void Button1_Click(object sender, System.EventArgs e)
{
    // バルーンチップを表示します。
    gcBalloonTip1.Show(button1, TipPosition.TopRight);
}
```

```vbnet
Imports GrapeCity.Win.Components

Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load
    Dim Label1 as Label = New Label()
    Label1.Text = "問い合わせ先："
    Label1.Location = New Point(0, 0)
    Label1.AutoSize = True
    GcContainer1.Controls.Add(Label1)

    Dim Label2 as Label = New Label()
    Label2.Text = "メシウス株式会社"
    Label2.Location = New Point(20, 15)
    Label2.AutoSize = true
    GcContainer1.Controls.Add(Label2)

    Dim LinkLabel1 as LinkLabel = New LinkLabel()
    LinkLabel1.Text = "https://developer.mescius.jp/"
    LinkLabel1.Location = New Point(20, 30)
    LinkLabel1.AutoSize = True
    GcContainer1.Controls.Add(LinkLabel1)
    
    ' バルーンチップに追加するコンテナコントロールをフォームから削除します。
    Controls.Remove(GcContainer1)

    ' ボタンにバルーンチップを設定します。
    Dim myTipInfo As New BalloonTipInformation
    GcBalloonTip1.SetBalloonTipInformation(Button1, myTipInfo)
    myTipInfo.Caption = "カスタムバルーンチップ"
    myTipInfo.Text = "バルーンチップにコンテナコントロールを追加"

    ' コンテナをバルーンチップに配置します。
    GcContainer1.Visible = True
    myTipInfo.CustomControl = GcContainer1
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
    ' バルーンチップを表示します。
    GcBalloonTip1.Show(Button1, TipPosition.TopRight)
End Sub
```

![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/06fadbb1-c461-433a-b385-ae4966e56069/images/gcballoontip.customcontrol.png)

## 関連トピック

[GcBalloonTipコンポーネント](gcdocsite__documentlink?toc-item-id=004e265f-b567-4c9f-8aee-3affb3902b5c)
[バルーンチップの表示](gcdocsite__documentlink?toc-item-id=9c715568-c0d2-40b6-b23f-dd958abebff4)