# BiddingStrategySelector
BiddingStrategySelector object displays the details of search results of auto bidding setting .
### Service
+ [BiddingStrategyService](../../services/BiddingStrategyService.md)

### Namespace
[BiddingStrategyService#Namespace](../../services/BiddingStrategyService.md#namespace)

| Field | Data Type | Description | ADD | SET | REMOVE |
|---|---|---|---|---|---|
| accountId | xsd:long | Account ID. | - | - | - |
| biddingStrategyIds[0...500] | xsd:long| Auto bidding ID.| - | - | - |
| biddingStrategyTypes[0...4] | enum <a href="BiddingStrategyType.md">BiddingStrategyType</a> | Auto bidding type. | - | - | - |
| paging | <a href="../Common/Paging.md">Paging</a> | Paging | - | - | - |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
