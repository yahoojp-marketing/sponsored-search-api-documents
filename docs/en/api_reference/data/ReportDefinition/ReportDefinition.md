

# ReportDefinition

ReportDefinition object describes report information.

### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Field | Type | Description | response | getReportFields | get | add | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | Account ID. | yes | - | - | - | - | |
| reportJobId | xsd:long | Report Job ID. | yes | - | - | - | Requirement | |
| reportJobStatus | enum [ReportJobStatus](./ReportJobStatus.md) | Status of Report Job. | yes | - | - | - | - | |
| reportJobErrorDetail | xsd:string | Error details of Report Job. | yes | - | - | - | - | |
| requestTime | xsd:string | Start time of Report Job request.<br/>*Displays in YYYY/MM/DD hh:mm:ss form.<br/>*hh will display in 24-hour time. | yes | - | - | - | - | |
| completeTime | xsd:string | Completion time of Report Job request.<br/>*Displays in YYYY/MM/DD hh:mm:ss form.<br/>*hh will display in 24-hour time. | yes | - | - | - | - | |
| reportDownloadURL | xsd:string | Download URL of report file. | yes | - | - | - | - | |
| reportName | xsd:string | Name of the report. | yes | - | - | Requirement | - | |
| reportType | enum [ReportType](./ReportType.md) | Type of report. | yes | - | - | Requirement | - | |
| dateRangeType | enum [ReportDateRangeType](./ReportDateRangeType.md) | Report range for running report. | yes | - | - | Requirement | - | |
| dateRange | [ReportDateRange](./ReportDateRange.md) | Date range of retrieving report, set by user. | yes | - | - | Optional | - | |
| fields[1...100] | xsd:string | Item name of the report.<br/>Can appoint the value retrieved from getReportFields. | yes | - | - | Requirement | - | |
| sortFields[0...1] | [ReportSortField](./ReportSortField.md) | Sort the specified field in order. | yes | - | - | Optional | - | |
| filters[0...6] | [ReportFilter](./ReportFilter.md) | Filter condition of report. | yes | - | - | Optional | - | |
| format | enum [ReportDownloadFormat](./ReportDownloadFormat.md) | File format of the report.<br/>*Default: CSV | yes | - | - | Optional | - | |
| encode | enum [ReportDownloadEncode](./ReportDownloadEncode.md) | Character encode setting of report.<br/>*Default: UTF-8 | yes | - | - | Optional | - | |
| language | enum [ReportLanguage](./ReportLanguage.md) | Language setting of report definition.<br/>*Default: JA | yes | - | - | Optional | - | |
| compress | enum [ReportCompressType](./ReportCompressType.md) | Select the compress type of report definition.<br/>*Default: NONE | yes | - | - | Optional | - | |
| includeZeroImpressions | enum [ReportIncludeZeroImpressions](./ReportIncludeZeroImpressions.md) | Select if include &#34;0 impression&#34; line in the report or not.<br/>*Default・FALSE(not include) | yes | - | - | Optional | - | |
| includeDeleted | enum [ReportIncludeDeleted](./ReportIncludeDeleted.md) | Select if include deleted items in report output.<br/>When select FALSE, deleted and paused items are out of output target.<br/>*Default・TRUE (to be output on the report) | yes | - | - | Optional<br/>※レポートタイプが以下の場合のみ。<br/>・CAMPAIGN<br/>・ADGROUP<br/>・AD<br/>・KEYWORDS<br/>・FEED_ITEM<br/>・AD_CUSTOMIZERS<br/>これ以外の場合はIgnore | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
