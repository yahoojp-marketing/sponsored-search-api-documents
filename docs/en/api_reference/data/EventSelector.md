# EventSelector
EventSelector object enables the target setting of acquiring operation history.
  
### Service
+ [AuditLogService](../services/AuditLogService.md)
 
<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>addJob</th>
 </tr>
 <tr>
  <td>entityType</td>
  <td>xsd:string<br><a href="AuditLogEntityType.md">AuditLogEntityType</a></td>
  <td>Type of entity to be acruied the operation history data.</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>eventTypes[1..3]</td>
  <td>enum<br><a href="AuditLogEventType.md">AuditLogEventType</a></td>
  <td>The operation event to be acruiqred data.</td>
  <td>Requirement</td>
 </tr>
 </table>
   
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
