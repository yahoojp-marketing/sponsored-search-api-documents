# BiddingStrategyOperation
BiddingStrategyOperation object displays the details of auto bidding details of designated campaign.

### Service
+ [BiddingStrategyService](../../services/BiddingStrategyService.md)

### Namespace
[BiddingStrategyService#Namespace](../../services/BiddingStrategyService.md#namespace)

| Field | Data type | Description | ADD | SET | REMOVE |
|---|---|---|---|---|---|
| Operation(inherited)||||||
| operator| enum Operator| Available to use: ADD, SET, REMOVE| Req| Req| Req |
| BiddingStrategyOperation||||||
| accountId| xsd:long| Account ID.| Req| Req<br>(notupdatable)| Req<br>(notupdatable) |
| operand[]| <a href="BiddingStrategy.md">BiddingStrategy</a>| List of Auto bidding| Req| Req| Req |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
