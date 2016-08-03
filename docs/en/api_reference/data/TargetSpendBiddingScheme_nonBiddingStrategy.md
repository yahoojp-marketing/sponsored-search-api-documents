# TargetSpendBiddingScheme [Non-BiddingStrategyService]
TargetSpendBiddingScheme object describes auto bidding setting for Maximize Clicks. <br>
(Object for services other than BiddingStrategyService)

### Service
+ [AdGroupService](../services/AdGroupService.md)
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
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
  <td colspan="8"><a href="./BiddingScheme_nonBiddingStrategy.md">BiddingScheme</a>(inherited)</td>
 </tr>
 <tr>
  <td>biddingStrategyType</td>
  <td>enum <a href="./BiddingStrategyType.md">BiddingStrategyType</a></td>
  <td>Type of Auto bididng.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td colspan="8">TargetSpendBiddingScheme</td>
 </tr>
  <tr>
  <td>bidCeiling</td>
  <td>xsd:long</td>
  <td>Bid amount limit.<br>*Limit range: 0 - 50000 <br>*If "0" is set, no bid limit.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
<tr>
  <td>spendTarget</td>
  <td>xsd:long</td>
  <td>Limit of Target Budget</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
