

# ReportFieldAttribute

ReportFieldAttribute object describes the available field to create report definition.

### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Field | Type | Description | response | getReportFields | get | add | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| fieldName | xsd:string | Field name. | yes | - | - | - | - | |
| displayFieldNameJA | xsd:string | Field name displayed in downloaded report (in Japanese). | yes | - | - | - | - | |
| displayFieldNameEN | xsd:string | Field name displayed in downloaded report (in English). | yes | - | - | - | - | |
| xmlAttributeName | xsd:string | XML attribute name displayed in donwloaded report. | yes | - | - | - | - | |
| fieldType | xsd:string | Type of field.<br/>Displays int, string, Enum, etc. | yes | - | - | - | - | |
| canSelect | xsd:boolean | Indicate if user can select the fields. | yes | - | - | - | - | |
| canFilter | xsd:boolean | Indicate if use can filter the fields. | yes | - | - | - | - | |
| impossibleCombinationFields[0..n] | xsd:string | Report fields which cannot be combined. | yes | - | - | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
