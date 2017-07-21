# CustomerSyncSelector
CustomerSyncSelector object describes the conditions for the target which Operation History is obtained.

### Service
+ [CustomerSyncService](../services/CustomerSyncService.md)

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
  <td>Account ID. </td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>campaignIds[]</td>
  <td>xsd:long</td>
  <td>Specify target campaign ID.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>entityType</td>
  <td>xsd:string<br>
  （<a href="./EntityType.md">EntityType</a>）  
  </td>
  <td>Specify target entity tipe. <br>
  *When requesting, specify the value defined on <a href="./EntityType.md">EntityType</a> in string type.
  </td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>eventTypes[]</td>
  <td>enum <a href="./EventType.md">EventType</a></td>
  <td>Specify target operation type.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>sourceTypes[]</td>
  <td>enum <a href="./SourceType.md">SourceType</a></td>
  <td>Specify which system operates.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>dateRange</td>
  <td><a href="./DateRange.md">DateRange</a></td>
  <td>Specify the period to check change entity.</td>
  <td>Optional</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
