# ReportDownloadUrl
Download URL including infomration of the report.
### Service
+ [ReportService](../services/ReportService.md)

| Field | Data Type | Description | 
|---|---|---|
| ReportRecord(inherited)|||
| accountId| xsd:long| Account Id. |
| reportJobId| xsd:long| Report job id. |
| reportId| xsd:long| Report definition id. |
| reportName| xsd:string| Report name. |
| requestTime| xsd:long| Request time of the report creation. |
| dateRangeType| enum <a href="./ReportDateRangeType.md">ReportDateRangeType</a>| Date range of report. |
| dateRange| <a href="./ReportDateRange.md">ReportDateRange</a>| Date range. |
| status| enum <a href="./ReportJobStatus.md">ReportJobStatus</a>| Status of the report. |
| ReportDownloadUrl|||
| downloadUrl| xsd:string| Report download URL. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
