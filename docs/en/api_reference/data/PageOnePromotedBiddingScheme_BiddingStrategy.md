# PageOnePromotedBiddingScheme [BiddingStrategyService]
PageOnePromotedBiddingScheme object displays Auto Bidding setting for Target position in search results. (This is for BiddingStrategyService)
### Service
+ [BiddingStrategyService](../services/BiddingStrategyService.md)

| Field | DataType | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| BiddingSchema(inherited)||||||
| biddingStrategyType| enum <a href="../data/BiddingStrategyType.md">BiddingStrategyType</a>| Auto bidding type| Req| Req<br>                        (notupdatable)| ─ |
| PageOnePromotedBiddingScheme||||||
| targetPositionType| enum <a href="../data/TargetPositionType.md">TargetPositionType</a>| Target position| Opt| Opt<br>                        (updatable)| ─ |
| bidCeiling| xsd:long| CPC limit (0-50000)<br>*No limits if numbers are set "0"| Opt| Opt<br>                        (updatable)| ─ |
| bidMultiplier| xsd:double| Bid multiplier<br>Available between 0.10 - 10.00 (-90% - +900%)| Opt| Opt<br>                        (updatable)| ─ |
| bidChangesForRaisesOnly| enum <a href="../data/BidChangesForRaisesOnly.md">BidChangesForRaisesOnly</a>| Auto or Manual setting of bids| Opt| Opt<br>                        (updatable)| ─ |
| raiseBidWhenBudgetConstrained| enum <a href="../data/RaiseBidWhenBudgetConstrained.md">RaiseBidWhenBudgetConstrained</a>| Bid raise setting from budget constraint| Opt| Opt<br>                        (updatable)| ─ |
| raiseBidWhenLowQualityScore| enum <a href="../data/RaiseBidWhenLowQualityScore.md">RaiseBidWhenLowQualityScore</a>| Bid raise setting for low quality keywords| Opt| Opt<br>                        (updatable)| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
