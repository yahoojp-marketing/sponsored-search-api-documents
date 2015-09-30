# ReportSelector
A requested report.
### Service
+ [ReportService](../services/ReportService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| Account ID. |
| reportIds[]| xsd:long| Report Definition Ids. |
| reportJobIds[]| xsd:long| Report job Ids. |
| reportJobStatuses[]| enum <a href="../data/ReportJobStatus.md">ReportJobStatus</a>| Status of report job. |
| paging| <a href="../data/Paging.md">Paging</a>| The starting index and number of results to return. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
