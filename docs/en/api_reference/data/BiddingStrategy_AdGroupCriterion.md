# BiddingStrategy [AdGroupCriterionService]
Bidding strategy object displays the type of strategy for Auto Bidding. (This is for AdGroupCriterionService)
### Service
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)

| Field | Data Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| biddingStrategyId| xsd:long| Auto bidding ID.| ─| ─| ─ |
| biddingStrategyName| xsd:string| Auto bidding name. (Can set up to 50 characters.)| ─| ─| ─ |
| biddingStrategyType| enum <a href="../data/BiddingStrategyType.md">BiddingStrategyType</a>| Auto bidding type.| ─| ─| ─ |
| biddingStrategySource| enum <a href="../data/BiddingStrategySource.md">BiddingStrategySource</a>| Bidding source.| ─| ─| ─ |
| biddingScheme| <a href="../data/BiddingScheme_BiddingStrategy.md">BiddingScheme</a><br><br> inherited <a href="../data/ManualCpcBiddingScheme.md">ManualCpcBiddingScheme</a><br><br> inherited <a href="../data/BudgetOptimizerBiddingScheme.md">BudgetOptimizerBiddingScheme </a><br><br> inherited <a href="../data/EnhancedCpcBiddingScheme_nonBiddingStrategy.md">EnhancedCpcBiddingScheme</a><br><br> inherited <a href="../data/PageOnePromotedBiddingScheme_nonBiddingStrategy.md">PageOnePromotedBiddingScheme </a><br><br> inherited <a href="../data/TargetCpaBiddingScheme_nonBiddingStrategy.md">TargetCpaBiddingScheme</a><br><br> inherited <a href="../data/TargetSpendBiddingScheme_nonBiddingStrategy.md">TargetSpendBiddingScheme</a><br><br> inherited <a href="../data/TargetRoasBiddingScheme_nonBiddingStrategy.md">TargetRoasBiddingScheme</a>| Auto bidding details| ─| ─| ─ |
| bid| enum <a href="../data/Bid_AdGroupCriterion.md">Bid</a>| Bids.| Opt| Opt<br>                     (updatable)| ─ |
| parentBiddingStrategyConfigurations[]| enum <a href="../data/BiddingStrategy_AdGroup.md">BiddingStrategy</a>| Bidding optimization setting (Upper entity)| ─| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
