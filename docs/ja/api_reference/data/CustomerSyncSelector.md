# CustomerSyncSelector
CustomerSyncSelectorオブジェクトは、操作履歴を取得する対象の条件を表します。
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
  <td>アカウントIDです。</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>campaignIds[]</td>
  <td>xsd:long</td>
  <td>対象となるキャンペーンIDです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>entityType</td>
  <td>xsd:string<br>
  （<a href="./EntityType.md">EntityType</a>）  
  </td>
  <td>対象となるエンティティのタイプを指定します。<br>
  ※リクエスト時は<a href="./EntityType.md">EntityType</a>で定義されている値をString型で指定します。
  </td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>eventTypes[]</td>
  <td>enum <a href="./EventType.md">EventType</a></td>
  <td>対象となる操作のタイプを指定します。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>sourceTypes[]</td>
  <td>enum <a href="./SourceType.md">SourceType</a></td>
  <td>どのシステムから行われた操作かを指定します。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>dateRange</td>
  <td><a href="./DateRange.md">DateRange</a></td>
  <td>変更状況を確認する期間を指定します。</td>
  <td>Optional</td>
 </tr>
 </table>
  
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
