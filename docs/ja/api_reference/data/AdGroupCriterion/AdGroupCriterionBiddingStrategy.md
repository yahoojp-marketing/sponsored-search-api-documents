# AdGroupCriterionBiddingStrategy
AdGroupCriterionBiddingStrategy オブジェクトは、入札方法を表します。<br>

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
  <td>biddingStrategyId</td>
  <td>xsd:long</td>
  <td> 自動入札IDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>biddingStrategyName</td>
  <td>xsd:string</td>
  <td>自動入札名です。<br>※50文字以内になります。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
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
  <td>biddingStrategySource</td>
  <td>enum <a href="BiddingStrategySource.md">BiddingStrategySource</a></td>
  <td>入札ソースです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>biddingScheme</td>
  <td><a href="BiddingScheme.md">BiddingScheme</a><br> inherited <a href="ManualCpcBiddingScheme.md">ManualCpcBiddingScheme</a><br> inherited <a href="BudgetOptimizerBiddingScheme.md">BudgetOptimizerBiddingScheme </a><br> inherited <a href="EnhancedCpcBiddingScheme.md">EnhancedCpcBiddingScheme</a><br> inherited <a href="PageOnePromotedBiddingScheme.md">PageOnePromotedBiddingScheme </a><br> inherited <a href="TargetCpaBiddingScheme.md">TargetCpaBiddingScheme</a><br> inherited <a href="TargetSpendBiddingScheme.md">TargetSpendBiddingScheme</a><br> inherited <a href="TargetRoasBiddingScheme.md">TargetRoasBiddingScheme</a></td>
  <td>自動入札設定の詳細です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>bid</td>
  <td><a href="Bid.md">Bid</a></td>
  <td>入札価格です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td>parentBiddingStrategyConfigurations[0...n]</td>
  <td><a href="AdGroupBiddingStrategy.md">AdGroupBiddingStrategy</a></td>
  <td>上位エンティティの入札設定です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
