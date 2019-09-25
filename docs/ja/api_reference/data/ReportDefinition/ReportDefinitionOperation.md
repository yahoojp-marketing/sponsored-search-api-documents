

# ReportDefinitionOperation

ReportDefinitionOperationオブジェクトは、操作の対象となるレポートおよび操作の内容を表します。

### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Field | Type | Description | response | getReportFields | get | add | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | - | - | Requirement | Requirement | |
| operand[0...30] | [ReportDefinition](./ReportDefinition.md) | 対象レポートの配列です。<br/>各配列には処理の対象となる操作対象 レポート情報が含まれます。 | yes | - | - | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
