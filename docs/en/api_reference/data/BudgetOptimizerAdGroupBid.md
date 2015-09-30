# BudgetOptimizerAdGroupBid
Maximum bid for AdGroup.
If BUDGET_OPTIMIZER is selected for BiddingStrategyType, the maximum bid for AdGroup will be ignored. And auto bid function without setting maximum bid will be valid.
### Service
+ [AdGroupService](../services/AdGroupService.md)

| Field | Data Type | Description | Restrictions | 
|---|---|---|---|
| AdGroupBid(inherited)||||||
| type| enum <a href="./BiddingStrategyType.md">BiddingStrategyType</a>| Bidding Strategy type.| -| -| - |
| BudgetOptimizerAdGroupBid||||||
| KeywordMaxCpc (updatable)| xsd:long| Max CPC (cost per click) bid for keyword targeting on search network.| Req| Opt| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
