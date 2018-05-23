# TargetRoasBiddingScheme
TargetRoasBiddingScheme object displays Auto Bidding setting for Target ROAS. 

### Service
+ [BiddingStrategyService](../../services/BiddingStrategyService.md)

### Namespace
[BiddingStrategyService#Namespace](../../services/BiddingStrategyService.md#namespace)

| Field | Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| BiddingScheme(inherited)||||||
| biddingStrategyType| enum <a href="BiddingStrategyType.md">BiddingStrategyType</a>| Auto bidding type.| Req| Req<br>                        (notupdatable)| ─ |
| TargetRoasBiddingScheme||||||
| targetRoas| xsd:double| Target ROAS<br>*ROAS: Return On Average Spend<br>*Setting limit: 0.01 〜1000.00（1%〜100000%）| Req| Opt<br>                        (updatable)| ─ |
| bidCeiling| xsd:long| CPC limit (0-50000)<br>*No limits if numbers are set "0"| Opt| Opt<br>                        (updatable)| ─ |
| bidFloor| xsd:long| Minimum CPC<br>*Set "0" to deactivate| Opt| Opt<br>                        (updatable)| ─ |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
