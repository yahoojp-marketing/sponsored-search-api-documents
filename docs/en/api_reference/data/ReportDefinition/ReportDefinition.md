# ReportDefinition
ReportDefinition object displays the report definition.

### Service
+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace
[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>get</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reportId</td>
  <td>xsd:long</td>
  <td>Report ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>reportName</td>
  <td>xsd:string</td>
  <td>Name of report.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reportType</td>
  <td>enum <a href="ReportType.md">ReportType</a></td>
  <td>Type of report.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>dateRangeType</td>
  <td>enum <a href="ReportDateRangeType.md">ReportDateRangeType</a></td>
  <td>Report range for running report.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>dateRange</td>
  <td><a href="DateRange.md">DateRange</a></td>
  <td>Date range of retrieving report, set by user.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>fields[1...100]</td>
  <td>xsd:string</td>
  <td>Item name of the report.<br>Can appoint the value retrieved from getReportFields.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>sortFields[0...1]</td>
  <td><a href="ReportSortField.md">ReportSortField</a></td>
  <td>Sort the specified field in order.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>filters[0...6]</td>
  <td><a href="ReportFilter.md">ReportFilter</a></td>
  <td>Filter condition of report.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>isTemplate</td>
  <td>enum <a href="ReportIsTemplate.md">ReportIsTemplate</a></td>
  <td>Select to create as template.<br>*Default: FALSE</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>intervalType</td>
  <td>enum <a href="ReportIntervalType.md">ReportIntervalType</a></td>
  <td>Settiing of creation timing of scheduled report.<br>*Default: ONETIME</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>specifyDay</td>
  <td>xsd:int</td>
  <td>Specifying the date of the report. <br>*Can select 1-31.<br>*Select "1" for beginning of month and "31" for end of month.<br>*Valid when intervalType: SPECIFYDAY.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>format</td>
  <td>enum <a href="ReportDownloadFormat.md">ReportDownloadFormat</a></td>
  <td>File format of the report.<br>*Default: CSV</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>encode</td>
  <td>enum <a href="ReportDownloadEncode.md">ReportDownloadEncode</a></td>
  <td>Character encode setting of report.<br>*Default: UTF-8</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>language</td>
  <td>enum <a href="ReportLanguage.md">ReportLanguage</a></td>
  <td>Language setting of report definition.<br>*Default: JA</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>compress</td>
  <td>enum <a href="ReportCompressType.md">ReportCompressType</a></td>
  <td>Select the compress type of report definition.<br>*Default: NONE</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>includeZeroImpressions</td>
  <td>enum <br><a href="ReportIncludeZeroImpressions.md">ReportIncludeZeroImpressions</a></td>
  <td>Select if include "0 impression" line in the report or not.<br>*Default・FALSE(not include)</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>includeDeleted</td>
  <td>enum <br><a href="ReportIncludeDeleted.md">ReportIncludeDeleted</a></td>
  <td>Select if include deleted items in report output.<br>
  When select FALSE, deleted and paused items are out of output target.<br>
  *Default・TRUE (to be output on the report)
  </td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*But for the following report types only:<br>・CAMPAIGN<br>・ADGROUP<br>・AD<br>・KEYWORDS<br>・FEED_ITEM<br>・AD_CUSTOMIZERS<br>*For other report types: Ignore
</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
