

# ReportDefinitionSelector

ReportDefinitionSelectorオブジェクトは、操作の対象とするレポートです。

### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Field | Type | Description | response | getReportFields | get | add | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | 検索条件： アカウントIDです。 | - | - | Requirement | - | - | |
| reportJobIds[0...500] | xsd:long | 検索条件： レポートジョブIDです。 | - | - | Optional | - | - | |
| reportTypes[0...15] | enum [ReportType](./ReportType.md) | 検索条件： レポートタイプです。 | - | - | Optional | - | - | |
| reportJobStatuses[0...4] | enum [ReportJobStatus](./ReportJobStatus.md) | 検索条件： ジョブステータスです。 | - | - | Optional | - | - | |
| paging | [Paging](../Common/Paging.md) | 検索条件： 取得範囲です。 | - | - | Optional | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
