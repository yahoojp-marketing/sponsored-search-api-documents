# BiddingStrategy
Bidding strategy object that displays the type of strategy for auto bidding. 
### Service
+ [BiddingStrategyService](../../services/BiddingStrategyService.md)

### Namespace
[BiddingStrategyService#Namespace](../../services/BiddingStrategyService.md#namespace)

| Field | Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| accountId| xsd:long| Account ID.| Req| Req<br>(notupdatable)| Req<br>(notupdatable) |
| biddingStrategyId| xsd:long| Auto bidding ID.| ─| Req<br>(notupdatable)| Req<br>(notupdatable) |
| biddingStrategyName| xsd:string| Auto bidding name. (Can set up to 50 characters.)| Req| Opt<br>                        (updatable)| ─ |
| biddingStrategyType| enum <a href="BiddingStrategyType.md">BiddingStrategyType</a>| Auto bidding type.| ─| ─| ─ |
| biddingScheme| <a href="BiddingScheme.md">BiddingScheme</a><br><br> inherited <a href="EnhancedCpcBiddingScheme.md">EnhancedCpcBiddingScheme</a><br><br> inherited <a href="PageOnePromotedBiddingScheme.md">PageOnePromotedBiddingScheme </a><br><br> inherited <a href="TargetCpaBiddingScheme.md">TargetCpaBiddingScheme</a><br><br> inherited <a href="TargetSpendBiddingScheme.md">TargetSpendBiddingScheme</a><br><br> inherited <a href="TargetRoasBiddingScheme.md">TargetRoasBiddingScheme</a>| Auto bidding details| Req| Opt<br>(updatable)| ─ |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
