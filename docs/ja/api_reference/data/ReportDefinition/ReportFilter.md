

# ReportFilter

ReportFilterオブジェクトは、レポートのフィルタ条件を表します。フィルタ条件は最大6つまで設定が可能です。

### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Field | Type | Description | response | getReportFields | get | add | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| field | xsd:string | フィルタ条件を設定する表示 項目です。 | yes | - | - | Requirement | - | |
| operator | enum [ReportOperator](./ReportOperator.md) | フィルタ条件を表す演算子です。 | yes | - | - | Requirement | - | |
| value[0...200] | xsd:string | 表示項目の条件値です。 | yes | - | - | Requirement | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
