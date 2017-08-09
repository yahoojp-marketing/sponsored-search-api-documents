# EventSelector
EventSelectorオブジェクトは、操作履歴の取得対象を設定します。
  
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
  <td>操作履歴の取得対象となるエンティティの種類です。</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>eventTypes[1..3]</td>
  <td>enum<br><a href="AuditLogEventType.md">AuditLogEventType</a></td>
  <td>操作履歴の取得対象となる操作です。</td>
  <td>Requirement</td>
 </tr>
 </table>
   
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
