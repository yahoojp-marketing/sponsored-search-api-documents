# BudgetOptimizer
BudgetOptimizer is an auto bidding in campaign level.
### Service
+ [CampaignService](../services/CampaignService.md)

| Field | Data Type | Description | Restrictions | 
|---|---|---|---|

| BiddingStrategy(inherited)||||||
| type| enum <a href="./BiddingStrategyType.md">BiddingStrategyType</a>| Bidding Strategy type.| Req| Req| - |
| BudgetOptimizerAdGroupBid||||||
| bidCeiling(updatable)| xsd:int| The maximum bid price for the case that you use BudgetOptimizer.※Please set the maximum bid price in the range 1 to 9,999 JPY. If not set, return an error.| -| -| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
