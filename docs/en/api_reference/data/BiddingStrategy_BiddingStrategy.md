# BiddingStrategy [BiddingStrategyService]
Bidding strategy object that displays the type of strategy for auto bidding. (This is for BiddingStrategyService)
### Service
+ [BiddingStrategyService](../services/BiddingStrategyService.md)

| Field | Data Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| accountId| xsd:long| Account ID.| Req| Req<br>                        (notupdatable)| Req<br>                        (notupdatable) |
| biddingStrategyId| xsd:long| Auto bidding ID.| ─| Req<br>                        (notupdatable)| Req<br>                        (notupdatable) |
| biddingStrategyName| xsd:string| Auto bidding name. (Can set up to 50 characters.)| Req| Opt<br>                        (updatable)| ─ |
| biddingStrategyType| enum <a href="../data/BiddingStrategyType.md">BiddingStrategyType</a>| Auto bidding type.| ─| ─| ─ |
| biddingScheme| <a href="../data/BiddingScheme_BiddingStrategy.md">BiddingScheme</a><br><br> inherited <a href="../data/EnhancedCpcBiddingScheme_BiddingStrategy.md">EnhancedCpcBiddingScheme</a><br><br> inherited <a href="../data/PageOnePromotedBiddingScheme_BiddingStrategy.md">PageOnePromotedBiddingScheme </a><br><br> inherited <a href="../data/TargetCpaBiddingScheme_BiddingStrategy.md">TargetCpaBiddingScheme</a><br><br> inherited <a href="../data/TargetSpendBiddingScheme_BiddingStrategy.md">TargetSpendBiddingScheme</a><br><br> inherited <a href="../data/TargetRoasBiddingScheme_BiddingStrategy.md">TargetRoasBiddingScheme</a>| Auto bidding details| Req| Opt<br>                        (updatable)| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
