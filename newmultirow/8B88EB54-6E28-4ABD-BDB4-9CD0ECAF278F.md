ユーザー定義のセルバリデータを作成するには、[CellValidator](gcdocsite__documentlink?toc-item-id=0e9f130c-4edb-4763-b295-3599a062604d)クラスを継承します。

## 最大文字数による検証

次のコードは、セルの値の最大文字数を検証するセルバリデータです。
```csharp
using GrapeCity.Win.MultiRow;

public class MaxLengthValidator : CellValidator
{
    protected override bool Validate(ValidateContext context)
    {
        if (context.EditedFormattedValue != null)
        {
            if (context.EditedFormattedValue.ToString().Length > this.MaxLength)
                return false;
        }
        return true;
    }

    public int MaxLength { get; set; }

    public override CellValidator Clone()
    {
        MaxLengthValidator validator = base.Clone() as MaxLengthValidator;
        validator.MaxLength = this.MaxLength;
        return validator;
    }
}
```

```vbnet
Imports GrapeCity.Win.MultiRow

Public Class MaxLengthValidator
    Inherits CellValidator

    Protected Overrides Function Validate(ByVal context As GrapeCity.Win.MultiRow.ValidateContext) As Boolean
        If context.EditedFormattedValue IsNot Nothing Then
            If context.EditedFormattedValue.ToString().Length > Me.MaxLength Then
                Return False
            End If
        End If
        Return True
    End Function

    Public MaxLength As Integer

    Public Overrides Function Clone() As GrapeCity.Win.MultiRow.CellValidator
        Dim validator As MaxLengthValidator = TryCast(MyBase.Clone(), MaxLengthValidator)
        validator.MaxLength = Me.MaxLength
        Return validator
    End Function

End Class
```
次のコードは、ユーザー定義のMaxLengthValidatorの使用例です。
```csharp
TextBoxCell textBoxCell1 = new TextBoxCell();

MaxLengthValidator maxLengthValidator1 = new MaxLengthValidator();
maxLengthValidator1.MaxLength = 2;
maxLengthValidator1.Actions.Add(new LineNotify());
textBoxCell1.Validators.Add(maxLengthValidator1);

Cell[] cells = { textBoxCell1 };
gcMultiRow1.Template = Template.CreateGridTemplate(cells);
gcMultiRow1.RowCount = 10;
```

```vbnet
Imports GrapeCity.Win.MultiRow

Dim TextBoxCell1 As New TextBoxCell

Dim MaxLengthValidator1 As New MaxLengthValidator()
MaxLengthValidator1.MaxLength = 2
MaxLengthValidator1.Actions.Add(New LineNotify())
TextBoxCell1.Validators.Add(MaxLengthValidator1)

Dim cells As Cell() = {TextBoxCell1}
GcMultiRow1.Template = Template.CreateGridTemplate(cells)
GcMultiRow1.RowCount = 10
```

## デザイナとユーザー定義のセルバリデータ

デザイナのCellValidatorコレクションエディタを使用してユーザー定義のセルバリデータを追加できます。
![](/DOCUMENT_SITE_LINK_PREFIX_HERE/document-site-files/images/f148c511-6e98-4b55-9904-150a375d5825/images/userguide/validation_userdefinedvalidator_01.png)
上記のMaxLengthValidatorを追加するには、次の手順を実行します。

1. ユーザー定義のセルバリデータMaxLengthValidatorを作成し、プロジェクトに追加する。
2. プロジェクトをビルドする。
3. 値を検証するセルを選択する。(例: textBoxCell1)
4. プロパティウィンドウでValidatorsプロパティを選択し、［...］ボタンをクリックする。
5. 表示されたCellValidatorコレクションエディタで左上のコンボボックスからMaxLengthValidatorを選択し、追加をクリックする。
6. 画面右のプロパティグリッドでMaxLengthプロパティを選択し、「5」を入力する。
7. 画面右のプロパティグリッドでActionsプロパティを選択し、［...］ボタンをクリックする。
8. 表示されたCellValidateActionコレクションエディタでLineNotifyを追加する。
9. ［OK］ボタンをクリックしてCellValidateActionコレクションエディタを閉じる。
10. ［OK］ボタンをクリックしてCellValidatorコレクションエディタを閉じる。

## 関連トピック

[ユーザー入力の検証](gcdocsite__documentlink?toc-item-id=0f3efc93-9866-452e-a9a6-3a1f0ecb6591)
[コントロールのイベントによる検証](gcdocsite__documentlink?toc-item-id=0e497c36-9fdf-421d-936a-bd7205764e8a)
[セルによる値の検証](gcdocsite__documentlink?toc-item-id=ab9b7b07-c4bf-4eff-a5d1-427115093507)
[検証の実行](gcdocsite__documentlink?toc-item-id=d9af300a-bc41-4bfd-90ab-a506563789cf)
[検証情報のカスタマイズ](gcdocsite__documentlink?toc-item-id=80e0bfb1-74a7-47e9-9c4a-f0c7d4eea41d)
[ユーザー定義の検証アクション](gcdocsite__documentlink?toc-item-id=a2acbd38-76de-4afd-a7ca-eb03c99ffa6f)