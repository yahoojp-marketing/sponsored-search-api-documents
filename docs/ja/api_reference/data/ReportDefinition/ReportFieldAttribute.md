

# ReportFieldAttribute

ReportFieldAttributeオブジェクトは、レポート定義の作成に使用できるフィールドを表します。

### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Field | Type | Description | response | getReportFields | get | add | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| fieldName | xsd:string | フィールド名です。 | yes | - | - | - | - | |
| displayFieldNameJA | xsd:string | ダウンロードされたレポートに 表示される日本語名です。 | yes | - | - | - | - | |
| displayFieldNameEN | xsd:string | ダウンロードされたレポートに 表示される英語名です。 | yes | - | - | - | - | |
| xmlAttributeName | xsd:string | ダウンロードしたレポートの XMLアトリビュートです。 | yes | - | - | - | - | |
| fieldType | xsd:string | フィールドの種類です。<br/>数字、文字列、Enum値等を表します。 | yes | - | - | - | - | |
| canSelect | xsd:boolean | ユーザーがこのフィールドを 選択できるかどうかを示します。 | yes | - | - | - | - | |
| canFilter | xsd:boolean | ユーザーがこのフィールドにフィルタを 適用できるかどうかを示します。 | yes | - | - | - | - | |
| impossibleCombinationFields[0..n] | xsd:string | 組み合わせができないレポートフィールドです。 | yes | - | - | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
