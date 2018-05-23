# CampaignRetargetingListOperation
CampaignRetargetingListOperation object holds the setting information of target list on campaign level to be object of mutate method oeration.

### Service
+ [CampaignRetargetingListService](../../services/CampaignRetargetingListService.md)

### Namespace
[CampaignRetargetingListService#Namespace](../../services/CampaignRetargetingListService.md#namespace)

### Inheritance
+ Operation

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td colspan="6">Operation(inherited)</td>
 </tr>
 <tr>
  <td>operator</td>
  <td>enum Operator</td>
  <td>Available to use: ADD, SET, REMOVE</td>
  <td colspan="6"></td>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
  <td>Requirement</td>
  <td>-</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>operand[1..1000]</td>
  <td><a href="CampaignRetargetingList.md">CampaignRetargetingList</a></td>
  <td>The setting information of target list on campaign level to be object of mutate method operation.</td>
  <td>Requirement</td>
  <td>-</td>
  <td>Requirement</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
