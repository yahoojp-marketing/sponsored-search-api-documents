# PageOnePromotedBiddingScheme [Non-BiddingStrategyService]
PageOnePromotedBiddingSchemeオブジェクトは、検索結果ページの目標掲載位置の自動入札設定情報を表します。<br>
（BiddingStrategyService以外用のオブジェクトです。）

### Service
+ [AdGroupCriterionService](../../services/AdGroupCriterionService.md)

### Namespace
[AdGroupCriterionService#Namespace](../../services/AdGroupCriterionService.md#namespace)

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
  <td>自動入札タイプです。</td>
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
  <td>掲載場所です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>bidCeiling</td>
  <td>xsd:long</a></td>
  <td>入札価格の上限です。<br>※制約値：0  ～ 50000<br>※「0」が設定された場合、上限設定は ありません。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>bidMultiplier</td>
  <td>xsd:double</a></td>
  <td>入札価格調整率です。<br>※0.10 ～ 10.00（-90% ～ +900%）の 範囲内のみ許容します。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>bidChangesForRaisesOnly</td>
  <td>enum <a href="BidChangesForRaisesOnly.md">BidChangesForRaisesOnly</a></a></td>
  <td>入札価格の自動・手動設定です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>raiseBidWhenBudgetConstrained</td>
  <td>enum <a href="RaiseBidWhenBudgetConstrained.md">RaiseBidWhenBudgetConstrained</a></a></td>
  <td>予算消化による広告掲載機会制限時の 入札価格の引き上げ設定です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>raiseBidWhenLowQualityScore</td>
  <td>enum <a href="RaiseBidWhenLowQualityScore.md">RaiseBidWhenLowQualityScore</a></a></td>
  <td>品質の低いキーワードに対する 入札価格の引き上げ設定です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
