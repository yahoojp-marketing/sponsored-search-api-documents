# CampaignRetargetingListSelector
CampaignRetargetingListSelector object holds search conditions (exec parameters) to get Target List settings on the campaign level.

### Service
+ [CampaignRetargetingListService](../../services/CampaignRetargetingListService.md)

### Namespace
[CampaignRetargetingListService#Namespace](../../services/CampaignRetargetingListService.md#namespace)

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
  <td>Search conditon: Account ID.</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>campaignIds[0..1000]</td>
  <td>xsd:long</td>
  <td>Search conditon: Campaign ID.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>targetListIds[0..1000]</td>
  <td>xsd:long</td>
  <td>Search conditon: Target List ID.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>excludedType</td>
  <td>enum <a href="ExcludedType.md">ExcludedType</a></td>
  <td>Search conditon: Settings of Include/Exclude.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>Search conditon: Page of results.</td>
  <td>Optional</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
