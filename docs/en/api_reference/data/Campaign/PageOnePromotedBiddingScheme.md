# PageOnePromotedBiddingScheme
PageOnePromotedBiddingScheme object displays Auto Bidding setting for Target position in search results. 

### Service
+ [CampaignService](../../services/CampaignService.md)

### Namespace
[CampaignService#Namespace](../../services/CampaignService.md#namespace)

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
  <td colspan="8"><a href="BiddingScheme.md">BiddingScheme</a>(inherited)</td>
 </tr>
 <tr>
  <td>biddingStrategyType</td>
  <td>enum <a href="BiddingStrategyType.md">BiddingStrategyType</a></td>
  <td>Type of Auto bidding.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td colspan="8">PageOnePromotedBiddingScheme</td>
 </tr>
 <tr>
  <td>targetPositionType</td>
  <td>enum <a href="TargetPositionType.md">TargetPositionType</a></a></td>
  <td>Position of Target.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>bidCeiling</td>
  <td>xsd:long</a></td>
  <td>Limit of bids (CPC).<br>* Limit range: 0 - 50000<br>* There will be no setting limit, if set as "0".</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>bidMultiplier</td>
  <td>xsd:double</a></td>
  <td>Bid multiplier.<br>* Limit range: 0.10 - 10.00 (-90% - +900%)</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>bidChangesForRaisesOnly</td>
  <td>enum <a href="BidChangesForRaisesOnly.md">BidChangesForRaisesOnly</a></a></td>
  <td>Auto or Manual setting of bids (CPC).</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>raiseBidWhenBudgetConstrained</td>
  <td>enum <a href="RaiseBidWhenBudgetConstrained.md">RaiseBidWhenBudgetConstrained</a></a></td>
  <td>Bid raise setting from budget constraint.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>raiseBidWhenLowQualityScore</td>
  <td>enum <a href="RaiseBidWhenLowQualityScore.md">RaiseBidWhenLowQualityScore</a></a></td>
  <td>Bid raise setting for low quality keywords.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
