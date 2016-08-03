# Criterion
Criterion object describes criteria information.<br>
*This criteria is for campaign.

### Service
+ [CampaignCriterionService](../services/CampaignCriterionService.md)

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
  <td>criterionId</td>
  <td>xsd:long</td>
  <td>Criterion ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>criterionTrackId</td>
  <td>xsd:long</td>
  <td>Criterion Track ID.<br>This is not returned for Negative keyword.</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>type</td>
  <td>enum <a href="./CriterionType.md">CriterionType</a></td>
  <td>Subtype of criteria of this instance.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この作品は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
