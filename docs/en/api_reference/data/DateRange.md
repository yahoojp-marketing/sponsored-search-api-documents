# DateRange
DateRange object displays the conditions and period to get Operation History.

### Service
+ [ReportDefinitionService](../services/ReportDefinitionService.md)
+ [AuditLogService](../services/AuditLogService.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>Start date of target date. *1-3</td>
  <td>-<br>For ReportDefinitionService : yes</td>
 <td>Optional<br>
 For 'addJob' of AuditLogService : Requirement</td>
  <td>-<br>For ReportDefinitionService : Ignore</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>End date of target date. *1-3</td>
  <td>-<br>For ReportDefinitionService : yes</td>
 <td>Optional<br>
 For 'addJob' of AuditLogService : Requirement</td>
  <td>-<br>For ReportDefinitionService : Ignore</td>
 </tr>
</table>

*1 The format for AuditLogService is specified as "YYYYMMDDhhmmss". It can be set at second bid level.<br>If it's not specified, the value'0:00:00' is set as default.<br>
　ex.) To set 2:05:35 PM on May 25, 2017, the value for this option is "20170525140535". <br>
*2 For ReportDefinitionService, it should be specified in "YYYMMDD" format.<br>
*3 Available date range :Jan 1, 1970 (19700101) - Dec 31, 2037 (20371231)<br>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
