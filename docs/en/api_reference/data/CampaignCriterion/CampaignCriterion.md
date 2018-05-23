# CampaignCriterion
CampaignCriterion object describes campaign criteria.

### Service
+ [CampaignCriterionService](../../services/CampaignCriterionService.md)

### Namespace
[CampaignCriterionService#Namespace](../../services/CampaignCriterionService.md#namespace)

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
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>Requirement<br>NoUpdatable</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>Campaign ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>Requirement<br>NoUpdatable</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>Campaign name.</td>
  <td>yes</td>
  <td>-</td>
  <td>Ignore</td>
  <td>-</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>criterionUse</td>
  <td>enum <a href="CampaignCriterionUse.md">CampaignCriterionUse</a></td>
  <td>Select the criterion's ability, individual bid available or excluded.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>Requirement<br>NoUpdatable</td>
 </tr>
  <tr>
  <td>criterion</td>
  <td><a href="Criterion.md">Criterion</a><br>inherited <a href="Keyword.md">Keyword</a></td>
  <td>Campaign criterion. </td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>Requirement<br>NoUpdatable</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
