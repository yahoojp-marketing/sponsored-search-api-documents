# CampaignBiddingStrategy
CampaignBiddingStrategy object describes Auto Bidding setting.

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
  <td>biddingStrategyId</td>
  <td>xsd:long</td>
  <td> Auto Bidding ID</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingStrategyName</td>
  <td>xsd:string</td>
  <td>Auto Bidding name.<br>*Up to 50 characters.</td>
  <td>yes</td>
  <td>-</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingStrategyType</td>
  <td>enum <a href="BiddingStrategyType.md">BiddingStrategyType</a></td>
  <td>Auto Bidding type.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingStrategySource</td>
  <td>enum <a href="BiddingStrategySource.md">BiddingStrategySource</a></td>
  <td>Bidding source.</td>
  <td>yes</td>
  <td>-</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingScheme</td>
  <td><a href="BiddingScheme.md">BiddingScheme</a><br> inherited <a href="ManualCpcBiddingScheme.md">ManualCpcBiddingScheme</a><br> inherited <a href="PageOnePromotedBiddingScheme.md">PageOnePromotedBiddingScheme </a><br> inherited <a href="TargetCpaBiddingScheme.md">TargetCpaBiddingScheme</a><br> inherited <a href="TargetSpendBiddingScheme.md">TargetSpendBiddingScheme</a><br> inherited <a href="TargetRoasBiddingScheme.md">TargetRoasBiddingScheme</a></td>
  <td>Details of Auto Bidding setting.</td>
  <td>yes</td>
  <td>-</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
