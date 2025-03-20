Modifiedプロパティを使用してグリッドの内容が変更されたかどうかを調べることができます。グリッド内のいずれかの値がエンドユーザーによって変更されると、[GcMultiRow.Modified](gcdocsite__documentlink?toc-item-id=5ad182a4-c47f-4fe2-9eb0-af4f6ffcc9dc)プロパティがTrueに設定されます。また、[Section.Modified](gcdocsite__documentlink?toc-item-id=a92195d0-dabc-41b5-9e12-c55a2b241615)プロパティを使用してセクション単位（列ヘッダセクション、行、列フッタセクション）でも変更状態を確認できます。

## データ変更の検出ルール

GcMultiRow.ModifiedプロパティとSection.Modifiedプロパティは、データが変更された場合に以下のルールに従ってお互いの値を変更します。

* Section.ModifiedプロパティにTrueが設定された場合、GcMultiRow.ModifiedプロパティはTrueに変更されます。
* Section.ModifiedプロパティにFalseが設定された場合、GcMultiRow.Modifiedプロパティは現在の値を保持します。
* GcMultiRow.ModifiedプロパティにTrueが設定された場合、Section.Modifiedプロパティは現在の値を保持します。
* GcMultiRow.ModifiedプロパティにFalseが設定された場合、すべてのSection.ModifiedプロパティはFalseに変更されます。

## サンプルコード

次の例は、Modifiedプロパティの基本的な使い方です。

```csharp
if (gcMultiRow1.Modified == true)
{
    Console.WriteLine("グリッドの内容は変更されています。");
}
```

```vbnet
If GcMultiRow1.Modified = True Then
    Console.WriteLine("グリッドの内容は変更されています。")
End If
```

## 関連トピック

[グリッド](gcdocsite__documentlink?toc-item-id=87ec6429-c3b9-4564-923f-f7c943ce00b9)
[テンプレートの割り当てと参照](gcdocsite__documentlink?toc-item-id=672f7dc1-1297-4293-87f6-f4d7ae30af83)
[編集モード](gcdocsite__documentlink?toc-item-id=1cd87acc-bf66-4bf7-bf75-b61800b830fb)
[選択モード](gcdocsite__documentlink?toc-item-id=05e1230b-6129-43d3-aa78-5b2cbf48ccba)
[表示モード](gcdocsite__documentlink?toc-item-id=e56c66d1-0481-4f06-a48c-d3c4d03893ef)
[文字列検索](gcdocsite__documentlink?toc-item-id=3b578791-7908-4795-8e61-b9f1e7339d21)
[スクロール](gcdocsite__documentlink?toc-item-id=2647ada3-b90d-4823-adf7-4fa4ef083123)
[選択セルのスタイル](gcdocsite__documentlink?toc-item-id=e04576cc-5bac-410c-9335-0dda134c922f)
[グリッドのスタイル設定](gcdocsite__documentlink?toc-item-id=77b3a184-61f9-4c3b-967b-dbb6f103acf0)
[ビジュアル スタイル](gcdocsite__documentlink?toc-item-id=860edbe2-0af7-4e60-876e-89187c42d483)
[ズーム](gcdocsite__documentlink?toc-item-id=d83eab82-185e-49f9-88b0-0fd8379d92b6)
[分割線とビューポート](gcdocsite__documentlink?toc-item-id=09f1eccf-76eb-4979-ac29-c97731b2357d)
[コンテキスト メニュー](gcdocsite__documentlink?toc-item-id=cbf794e7-3362-41e9-b625-bd3e8130611b)
[ショートカット キー](gcdocsite__documentlink?toc-item-id=9cdbb6ad-e84e-441f-8f3f-ddd78af7b429)
[リサイズ](gcdocsite__documentlink?toc-item-id=4657f508-867c-455c-81b4-858e8f1d18d7)
[リサイズ時のオフセット処理](gcdocsite__documentlink?toc-item-id=e7471d46-a6b0-47fe-982d-8d4b7561d4e3)
[セルの移動方法の取得](gcdocsite__documentlink?toc-item-id=f3a0271e-fbeb-46ba-aa76-b99352d3e55c)
[セルの自動マージ](gcdocsite__documentlink?toc-item-id=1d1e19b2-4282-48a3-ad92-603f73b3cc38)
[新規行の上部表示](gcdocsite__documentlink?toc-item-id=881b6d3e-e4d3-4271-b874-a972e9aef2c8)
[列の展開／折り畳み](gcdocsite__documentlink?toc-item-id=421066a5-9bfa-427f-a980-245ff290f1af)
[セル幅の自動調整](gcdocsite__documentlink?toc-item-id=0fb2df6a-d9df-47d2-8ae9-50185f2c488d)
[SPREADスタイルの適用](gcdocsite__documentlink?toc-item-id=9d7078b7-c6b3-420b-a282-9d08e8135b48)
[既定の設定における留意点](gcdocsite__documentlink?toc-item-id=707e6129-7446-4ccf-9b4b-574225dc0b02)
[パフォーマンスを向上するためのヒント](gcdocsite__documentlink?toc-item-id=78fbc71a-7acb-4af3-ae37-953454f8dece)