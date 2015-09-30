# ReportRecord
information of the report.
### Service
+ [ReportService](../services/ReportService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| Account Id. |
| reportJobId| xsd:long| Report Job Id. |
| reportId| xsd:long| Report Definition Id. |
| reportname| xsd:string| Report name. |
| requestTime| xsd:long| Request time ot the job. |
| completeTime| xsd:long| Complete time of the job. |
| dateRangeType| enum <a href="../data/ReportDateRangeType.md">ReportDateRangeType</a>| Date range of report. |
| dateRange| <a href="../data/ReportDateRange.md">ReportDateRange</a>| Date range. |
| status| enum <a href="../data/ReportJobStatus.md">ReportJobStatus</a>| Report status. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
