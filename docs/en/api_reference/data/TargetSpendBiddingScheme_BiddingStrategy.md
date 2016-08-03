# TargetSpendBiddingScheme [BiddingStrategyService]
TargetSpendBiddingScheme object describes Auto Bidding setting for Maximize Clicks. (Object for BiddingStrategyService)
### Service
+ [BiddingStrategyService](../services/BiddingStrategyService.md)

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
  <td colspan="8"><a href="./BiddingScheme_BiddingStrategy.md">BiddingSchema</a>(inherited)</td>
 </tr>
 <tr>
  <td>biddingStrategyType</td>
  <td>enum <a href="../data/BiddingStrategyType.md">BiddingStrategyType</a></td>
  <td>Auto Bidding type.</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">TargetSpendBiddingScheme</td>
 </tr>
 <tr>
  <td>bidCeiling</td>
  <td>xsd:long</td>
  <td>Bid amount limit (0-50000).<br>*No limits if "0" is set.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>(updatable)</td>
  <td>-</td>
 </tr>
 <tr>
  <td>spendTarget</td>
  <td>xsd:long</td>
  <td>Target daily budget (limit a day).<br>*No target budget if "0" is set.<br>*If specified "0", existing target budget is released.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>(updatable)</td>
  <td>-</td>
 </tr>
</table>
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
