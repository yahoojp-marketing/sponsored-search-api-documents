# ReportDefinitionField
ReportDefinitionFieldオブジェクトは、ReportDefinitionの作成に使用できるフィールドを表します。
### Service
+ [ReportDefinitionService](../services/ReportDefinitionService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| filedName| xsd:string| フィールド名です。 |
| displayFiledName| xsd:string| ダウンロードされたレポートに表示される名前です。 |
| xmlAttributeName| xsd:string| ダウンロードしたレポートのXMLアトリビュートです。 |
| fieldType| xsd:string| フィールドのタイプです。 |
| enumValues[]| xsd:string| フィールドがenumeration型の場合、対応するフィールドに使用できるenumerationのリストです。 |
| canSelect| xsd:boolean| ユーザーがこのフィールドを選択できるかどうかを示します。 |
| canFilter| xsd:boolean| ユーザーがこのフィールドにフィルタを適用できるかどうかを示します。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
