# ReportDefinition
ReportDefinition object displays the report definition.
### Service
+ [ReportDefinitionService](../services/ReportDefinitionService.md)

| Field | Data Type | Description | Restriction | 
|---|---|---|---|
| reportId| xsd:long| Report definition ID| -| Req| Req |
| accountId| xsd:long| Account ID| Req| Req| Req |
| campaignIds[]| xsd:long| Campaign IDs.| Opt| -| - |
| adGroupIds[]| xsd:long| Ad Group IDs.| Opt| -| - |
| kwIds[]| xsd:long| Keyword IDs.| Opt| -| - |
| adIds[]| xsd:long| Ad IDs.| Opt| -| - |
| feedItemIds[]| xsd:long| Feed Item IDs.| Opt| -| - |
| feedFolderIds[]| xsd:long| Data auto insertion IDs.| Opt| -| - |
| biddingStrategyIds[]| xsd:long| Auto bidding IDs.| Opt| -| - |
| targetListIds[]| xsd:long| Target list IDs.| Opt| -| - |
| reportName| xsd:string| Name of report definition.| Req| Opt| - |
| reportType| enum <a href="./ReportType.md">ReportType</a>| Type of the report.| Req| -| - |
| dateRangeType| enum <a href="./ReportDateRangeType.md">ReportDateRangeType</a>| Report range for running report.| Req| -| - |
| dateRange| <a href="./ReportDateRange.md">ReportDateRange</a>| Date range of retrieving report, set by user.It is required when dataRangeType is set as CUSTOM DATE.| Opt| -| - |
| filters[]| <a href="./ReportFilter.md">ReportFilter</a>| Filter condition of report.| Opt| -| - |
| segments[]| xsd:string| Filter condition for grouping.<br>Please see the reference for the details in report segments.| Opt| -| - |
| sort| xsd:string| Sort in ascending or descending order.<br>Can sort by inputing “+” or “-“ before the field name.<br>Field name can be retrieved by getReportFields.| Req| -| - |
| fields[]| xsd:string| Item name of the report.<br>Can appoint the value retrieved from getReportFields.| Req| -| - |
| format| enum <a href="./ReportDownloadFormat.md">ReportDownloadFormat</a>| File format of the report.| Req| -| - |
| encode| enum <a href="./ReportDownloadEncode.md">ReportDownloadEncode</a>| Character encoding of the report.| Req| -| - |
| zip| enum <a href="./ReportZip.md">ReportZip</a>| Compress or uncompress of the report.| Req| -| - |
| lang| enum <a href="./ReportLang.md">ReportLang</a>| Language setting of the report column.| Opt| -| - |
| frequency| enum <a href="./ReportFrequency.md">ReportFrequency</a>| Schedule of report creation.| Opt| -| - |
| specifyDay| xsd:int| Specifying the date of the report. <br>It is required when ReportFrequency is appointed as SPECIFYDAY.| Opt| Opt| - |
| addTemplate| enum <a href="./ReportAddTemplate.md">ReportAddTemplate</a>| Set the definition for a report template. <br>The maximum number of template is 30 by the total of standard and on-behalf of authorization. <br>It cannot be shared between standard and on behalf.| Req| -| - |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
