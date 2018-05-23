# CampaignRetargetingList
CampaignRetargetingList object holds the setting information of Target List on campaign level.

### Service
+ [CampaignRetargetingListService](../../services/CampaignRetargetingListService.md)

### Namespace
[CampaignRetargetingListService#Namespace](../../services/CampaignRetargetingListService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>Campaign ID.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>Name of campaign.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>criterionTargetList</td>
  <td><a href="CriterionTargetList.md">CriterionTargetList</a></td>
  <td>Target List.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>excludedType</td>
  <td>enum <a href="ExcludedType.md">ExcludedType</a></td>
  <td>Include/Exclude setting of Target List.</td>
  <td>yes</td>
  <td>Optional<br>default:INCLUDED</td>
  <td>Optional</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>bidMultiplier</td>
  <td>xsd:double</td>
  <td>Bid adjustment rate.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
