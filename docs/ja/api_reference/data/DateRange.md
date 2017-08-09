# DateRange
DateRangeオブジェクトは操作履歴を取得する条件、期間を示します。

### Service
+ [CustomerSyncService](../services/CustomerSyncService.md)
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
  <td>対象期間の開始日です。※1-3</td>
  <td>-<br>※ReportDefinitionServiceの場合、yes</td>
 <td>Optional<br>
 ※AuditLogServiceのaddJobの場合、Requirement</td>
  <td>-<br>※ReportDefinitionServiceの場合、Ignore</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>対象期間の終了日です。※1-3</td>
  <td>-<br>※ReportDefinitionServiceの場合、yes</td>
 <td>Optional<br>
 ※AuditLogServiceのaddJobの場合、Requirement</td>
  <td>-<br>※ReportDefinitionServiceの場合、Ignore</td>
 </tr>
</table>

※1 CustomerSyncServiceおよびAuditLogServiceでの指定は「YYYYMMDDhhmmss」形式です。秒単位まで指定できます。<br>時間の指定がない場合は、0:00:00として扱われます。<br>
　【例】2016年5月25日 午後2時5分35秒に設定したい場合：20160525140535<br>
※2 ReportDefinitionServiceでの指定は「YYYMMDD」形式です<br>
※3 日付は19700101～20371231まで設定可能です。<br>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
