# AuditLogSelector
AuditLogSelectorオブジェクトは、登録したジョブを照会するための検索条件を保持します。
 
### Service
+ [AuditLogService](../services/AuditLogService.md)
 
<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>get</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>jobIds[0..1000]</td>
  <td>xsd:long</td>
  <td>登録したジョブのIDです。</td>
  <td>Optional</td>
 </tr>
  <tr>
  <td>jobStatuses[0..4]</td>
  <td>enum<br><a href="./AuditLogJobStatus.md">AuditLogJobStatus</a></td>
  <td>登録したジョブのステータスです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="./Paging.md">Paging</a></td>
  <td>データの取得範囲です。</td>
  <td>Optional</td>
 </tr>
</table>
  
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
