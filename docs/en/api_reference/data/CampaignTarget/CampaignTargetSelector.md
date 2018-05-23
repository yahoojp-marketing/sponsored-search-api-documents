# CampaignTargetSelector
CampaignTargetSElector object describes the targeting settings on the campaign to be operated.
### Service
+ [CampaignTargetService](../../services/CampaignTargetService.md)

### Namespace
[CampaignTargetService#Namespace](../../services/CampaignTargetService.md#namespace)

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
  <td>Account ID.</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>campaignIds[0..500]</td>
  <td>xsd:long</td>
  <td>Campaign ID.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>targetIds[0..500]</td>
  <td>xsd:long</td>
  <td>Target ID.</td>
  <td>Optional</td>
 </tr>
  <tr>
  <td>targetTypes[0..4]</td>
  <td>enum<br><a href="TargetType.md">TargetType</a></td>
  <td>Targeting type.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>excludedType</td>
  <td>enum<br><a href="ExcludedType.md">ExcludedType</a></td>
  <td>Included or Excluded setting for displaying ads.<br>*It is available only with targetTypes 'LOCATION'.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>platformTypes</td>
  <td>enum<br><a href="PlatformType.md">PlatformType</a></td>
  <td>Target device.<br>*Ignore for cases other than Device Targeting.</td>
  <td>Optional</td>
 </tr> 
  <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>Holds the paging parameters such as starting index.</td>
  <td>Optional</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
