# CampaignValues
CampaignValues object is campaign information including its operation results.

### Service
+ [CampaignService](../services/CampaignService.md)


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
  <td colspan="8"><a href="./ReturnValue.md">ReturnValue</a>(inherited)</td>
 </tr>
 <tr>
  <td>operationSucceeded</td>
  <td>xsd:boolean</td>
  <td>Result of process.</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td>error[]</td>
  <td><a href="./Error.md">Error</a></td>
  <td>Error details from mutate process.</td>
  <td colspan="7"></td>
 </tr>
 <tr>
  <td colspan="8">CampaignValues</td>
 </tr>
 <tr>
  <td>campaign</td>
  <td><a href="./Campaign.md">Campaign</a></td>
  <td>Result of get/mutate process per Campaign.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
